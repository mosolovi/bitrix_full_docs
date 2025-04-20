[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[Пользовательские свойства](/api_help/iblock/classes/user_properties/index.php)

GetPublicViewHTML (доступен с 6.5.2)

GetPublicViewHTML
=================

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
string
CIBlockProperty*::GetPublicViewHTML(
	array arProperty,
	array value,
	array strHTMLControlName
);Копировать
```

Метод должна вернуть безопасный HTML отображения значения свойства в публичной части сайта. Если она вернет пустое значение, то значение отображаться не будет. Метод статический при использовании штатных свойств. У свойств, созданных клиентом, обязан быть статическим при использовании php7.

**Примечание:** вызывается из метода CIBlockFormatProperties::GetDisplayValue, которая используется компонентами модуля информационных блоков для форматирования значений свойств.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| arProperty | Метаданные свойства. См. [Свойства элементов инфоблока](/api_help/iblock/fields.php#fproperty) |
| value | Значение свойства. Массив вида:  ``` array( 	"VALUE" => значение, ); Копировать ``` |
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
	function GetPublicViewHTML($arProperty, $value, $strHTMLControlName)
	{
		if(strlen($value["VALUE"])>0)
			return str_replace(" ", "&nbsp;", htmlspecialcharsex($value["VALUE"]));
		else
			return '';
	}
}
?>Копировать
```

Новинки документации в соцсетях: