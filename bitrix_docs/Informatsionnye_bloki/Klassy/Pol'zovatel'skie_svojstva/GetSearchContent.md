[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[Пользовательские свойства](/api_help/iblock/classes/user_properties/index.php)

GetSearchContent (доступен с 8.6.1)

GetSearchContent
================

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
string
CIBlockProperty*::GetSearchContent(
	array arProperty,
	array value,
	array strHTMLControlName
);Копировать
```

Метод должна вернуть представление значения свойства для модуля поиска. Метод статический при использовании штатных свойств. У свойств, созданных клиентом, обязан быть статическим при использовании php7.

**Примечание:** вызывается при индексации элементов инфоблока модулем поиска. Если для свойства не определен этот метод, но есть метод [GetPublicViewHTML](/api_help/iblock/classes/user_properties/GetPublicViewHTML.php), то будет вызван он. После удаления разметки HTML в поисковый индекс будет занесен его результат.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| arProperty | Метаданные свойства. См. [Свойства элементов инфоблока](/api_help/iblock/fields.php#fproperty) |
| value | Значение свойства. Массив вида:  ``` array( 	"VALUE" => значение, );Копировать ``` |
| strHTMLControlName | Пустой массив. |

#### Возвращаемое значение

Строка.

### Смотрите также

* [Свойства элементов инфоблока](/api_help/iblock/fields.php#fproperty)
* [GetUserTypeDescription](/api_help/iblock/classes/user_properties/GetUserTypeDescription.php)

### Примеры использования

```
<?
class CIBlockPropertyMyDateTime
{
	function GetSearchContent($arProperty, $value, $strHTMLControlName)
	{
		if(strlen($value["VALUE"])>0)
			return $value["VALUE"];
		else
			return '';
	}
}
?>Копировать
```

Новинки документации в соцсетях: