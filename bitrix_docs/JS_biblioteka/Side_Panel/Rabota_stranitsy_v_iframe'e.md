[JS библиотека](/api_help/js_lib/index.php)

[Side Panel](/api_help/js_lib/sidepanel/index.php)

Работа страницы в iframe'е

Работа страницы в iframe'е
==========================

Если в iframe'е слайдера открыть обычную страницу сайта, то она покажется вместе с общим дизайном (меню, шапка, подвал). Для этого режима необходимо адаптировать вывод компонента. При открытии страницы слайдер всегда добавляет в адрес параметр `IFRAME=Y`. По этому параметру можно понять, что страница открылась в iframe'е и изменить итоговую верстку.

В упрощенном виде адаптация под слайдер выглядит так:

```
<?
if (isset($_REQUEST["IFRAME"]) && $_REQUEST["IFRAME"] === "Y")
{
	$APPLICATION->RestartBuffer(); //сбрасываем весь вывод
	?>
	<!DOCTYPE html>
	<html>
	<head>
		<?$APPLICATION->ShowHead(); ?>
	</head>
	<body>
		<?
			//Контент компонента
		?> 
	</body>
	</html><?
}
else
{
	//Контент компонента
}
?>Копировать
```

Чтобы не дублировать код, желательно использовать [компонент-обертку](https://dev.1c-bitrix.ru/api_d7/bitrix/ui/sidepanel_wrapper/index.php).

```
//class.php
<?
if (!defined('B_PROLOG_INCLUDED') || B_PROLOG_INCLUDED!==true)
{
	die();
}
class SliderWrapperComponent extends \CBitrixComponent
{
	public function executeComponent()
	{
		/** @var CMain $APPLICATION */
		global $APPLICATION;
		$APPLICATION->RestartBuffer();
		if (!isset($this->arParams['COMPONENT_PARAMS']) || !is_array($this->arParams['COMPONENT_PARAMS']))
		{
			$this->arParams['COMPONENT_PARAMS'] = array();
		}
		$this->arParams['COMPONENT_PARAMS']['IFRAME'] = true;
		$this->includeComponentTemplate();
		require($_SERVER['DOCUMENT_ROOT'] . '/bitrix/modules/main/include/epilog_after.php');
		exit;
	}
}Копировать
```

  

```
//template.php
<?
if (!defined('B_PROLOG_INCLUDED') || B_PROLOG_INCLUDED !== true) 
{
	die();
}
CJSCore::Init("sidepanel");
?>
<!DOCTYPE html>
<html>
<head>
	<script type="text/javascript">
		// Prevent loading page without header and footer
		if(window == window.top)
		{
			window.location = "<?=CUtil::JSEscape($APPLICATION->GetCurPageParam('', array('IFRAME'))); ?>";
		}
	</script>
	<?$APPLICATION->ShowHead();?>
</head>
<body class="disk-slider-body">
	
	<div class="disk-slider-title"><? $APPLICATION->ShowTitle(); ?></div>
	<div class="disk-slider-workarea">
		<div class="disk-slider-sidebar"><? $APPLICATION->ShowViewContent("sidebar"); ?></div>
		<div class="disk-slider-content">
			<?
			$APPLICATION->IncludeComponent(
				$arParams['COMPONENT_NAME'],
				$arParams['COMPONENT_TEMPLATE_NAME'],
				$arParams['COMPONENT_PARAMS']
			);
			?>
		</div>
	</div>
</body>
</html>
<?Копировать
```

```
//page.php - страница комплексного компонента
if (isset($_REQUEST['IFRAME']) && $_REQUEST['IFRAME'] == 'Y')
{
	$APPLICATION->IncludeComponent(
		'mycompany:slider.wrapper',
		'',
		array(
			'COMPONENT_NAME' => 'mycompany:mycomponent',
			'COMPONENT_TEMPLATE_NAME' => '',
			'COMPONENT_PARAMS' => $componentParameters,
		)
	);
}
else
{
	$APPLICATION->IncludeComponent(
		'mycompany:mycomponent',
		'',
		$componentParameters
	);
}Копировать
```

Установите контейнеру компонента минимальную ширину (min-width). На малых разрешениях в слайдере появится горизонтальный скроллинг. Это предотвратит "наезд" элементов дизайна друг на друга.

Ссылки внутри iframe'а обрабатываются по тем же правилам [BX.SidePanel.Instance.bindAnchors](/api_help/js_lib/sidepanel/sidepanel_instance.php#bindAnchors), что и на родительской странице. Если по нажатию ссылки правила не совпали, переход будет осуществлен обычным образом - в iframe загрузится страница вместе с дизайном шаблона сайта. Для подобных ссылок можно либо указать атрибут `target="_top"` (ссылка откроется в родительском окне), либо добавить параметр `IFRAME=Y` для открытия страницы, адаптированной под слайдер.

`$APPLICATION->ShowHead()` подключит в iframe'е стили шаблона сайта (**template\_styles.css**) и стили компонента. Стили шаблона сайта (как правило, это CSS-селектор **body {}**) могут повлиять на внешний вид содержимого.

Названия CSS-классов дополнительных элементов оформления (заголовок, сайдбар) должны иметь уникальные названия и не пересекаться с названиями CSS-классов шаблона сайта.

Внутри iframe'а к слайдеру можно обращаться так же как и в родительской странице через [BX.SidePanel.Instance](/api_help/js_lib/sidepanel/sidepanel_instance.php). Этот подход требует на странице iframe'а подключить слайдер *CJSCore::Init("sidepanel")*.

Если на странице подключается не `/bitrix/header.php`, а `/bitrix/modules/main/include/prolog_before.php`, то помимо *CJSCore::Init("sidepanel");* нужно также добавить `$APPLICATION->ShowHeadStrings();`.

Новинки документации в соцсетях: