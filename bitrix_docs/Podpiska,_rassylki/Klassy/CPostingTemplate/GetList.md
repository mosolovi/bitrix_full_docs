[Подписка, рассылки](/api_help/subscribe/index.php)

[Классы](/api_help/subscribe/classes/index.php)

[CPostingTemplate](/api_help/subscribe/classes/cpostingtemplate/index.php)

GetList (доступен с 4.0.5)

GetList
=======

```
array
CPostingTemplate::GetList();Копировать
```

Метод возвращает список шаблонов. Метод статический.

#### Параметры

Метод не имеет параметров.

#### Возвращаемые значения

Возвращается массив относительных путей к подкаталогам каталога `/bitrix/php_interface/subscribe/templates`.

#### Пример использования

```
<?
//get template directories
$arTemplates = CPostingTemplate::GetList();
foreach($arTemplates as $template_dir):
?>
	<p><?echo $template_dir?></p>
<?
endforeach;
?>Копировать
```

Новинки документации в соцсетях: