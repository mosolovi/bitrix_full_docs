[Информационные блоки](/api_help/iblock/index.php)

[Функции](/api_help/iblock/functions/index.php)

GetIBlockElement (доступна с 3.0.5)

GetIBlockElement
================

Включить вкладки

Описание и параметры

Возвращаемое значение

Смотрите также

Примеры использования

### Описание и параметры

```
array 
GetIBlockElement(
	int ID,
	string type = ""
);Копировать
```

Функция возвращает информационный элемент с кодом *ID*. Функция-помошник, которая выбирает все базовые поля элемента, его свойства и информацию об инфоблоке. Использует [GetList](/api_help/iblock/classes/ciblockelement/getlist.php).

**Примечание:** функция является устаревшей, оставлена для обратной совместимости. Рекомендуется использоваться метод [GetList](/api_help/iblock/classes/ciblockelement/getlist.php).

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| ID | ID элемента. |
| type | Тип информационного блока. Устанавливается в настройках модуля. Если задан, то при выборке проверяется чтобы элемент соответствовал этому типу.   Необязательный. По умолчанию на элемент не накладываются ограничения по типу. |

### Возвращаемое значение

Функция возвращает массив [полей информационного элемента](/api_help/iblock/fields.php#felement) и дополнительно следующие поля:

| Поле | Значение |
| --- | --- |
| IBLOCK\_NAME | Название информационного блока. |
| PROPERTIES | Массив значений свойств, имеющий в качестве индексов "Символьный код свойства" (задается в настройках информационного блока) или, если код не задан, то уникальное ID свойства. Значением каждого свойства будет массив вида:  ``` Array(  	"NAME"=>"название свойства",  	"DEFAULT_VALUE"=>"значение свойства по умолчанию",  	"VALUE"=>"значение свойства или массив значений свойств, если свойство множественное",  	"VALUE_ENUM_ID"=>"Код значения свойства типа <Список>"  )Копировать ``` |

Если заданным параметрам не найден элемент, функция вернет *false*.
  
Выборка элемента происходит только из активных элементов инфоблока, неактивный элемент выбран быть не может.

**Примечание:** все возвращаемые поля преобразованы в "HTML безопасный" вид, а в полях (LIST\_PAGE\_URL - списка элементов и DETAIL\_PAGE\_URL - детального просмотра) с шаблонами URL-ов к страницам будут заменены параметры `#SITE_DIR#`, `#IBLOCK_ID#`, `#EXTERNAL_ID#` и `#ID#`.

### Смотрите также

* [Поля информационного элемента](/api_help/iblock/fields.php#felement)

### Примеры использования

```
<?
require($_SERVER['DOCUMENT_ROOT'].'/bitrix/header.php');
$APPLICATION->SetTitle('Карточка товара');
// подключим модуль и выберем элемент ID типа product
$arIBlockElement = false;
if(CModule::IncludeModule('iblock') && ($arIBlockElement = GetIBlockElement($ID, 'product')))
{
	// В заголовок страницы вставим название элемента
	$APPLICATION->SetTitle($arIBlockElement['NAME']);
	// В навигационную цепочку вставим название и ссылку на текущий информационный блок
	$APPLICATION->AddChainItem($arIBlockElement['IBLOCK_NAME'], 'products.php?ID='.$arIBlockElement['IBLOCK_ID']);
	// выведем детальную картинку
	echo ShowImage($arIBlockElement['DETAIL_PICTURE'], 150, 150, 'border="0"', '', true);
	// выведем детальное описание
	echo $arIBlockElement['DETAIL_TEXT'].'<br>';
	// выведем значение свойства с кодом PRICE
	echo $arIBlockElement['PROPERTIES']['PRICE']['VALUE'].'<br>';
	// вывeдем оставшиеся свойства
	$arProps = $arIBlockElement['PROPERTIES'];
	foreach($arProps as $property_code=>$arValue)
	{
		// если это свойство с кодом PRICE или значение свойства не введено - пропустим
		if($property_code=='PRICE' 
			|| (!is_array($arValue['VALUE']) && strlen($arValue['VALUE'])<=0) 
			|| (is_array($arValue['VALUE']) && count($arValue['VALUE'])<=0)
		)
		continue;
		// выведем пару "Название: значение"
		if(!is_array($arValue['VALUE']))
			echo $arValue['NAME'].": ".$arValue['VALUE'];
		else
		{
			echo $arValue['NAME'].': ';
			foreach($arValue['VALUE'] as $val)
			{
				echo $val.'<br>';
			}
		}
	}
}
else
	echo ShowError('Новость не найдена');
require($_SERVER["DOCUMENT_ROOT"].'/bitrix/footer.php");
?>Копировать
```

Новинки документации в соцсетях: