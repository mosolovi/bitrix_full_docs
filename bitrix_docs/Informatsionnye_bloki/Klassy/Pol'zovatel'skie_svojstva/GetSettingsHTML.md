[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[Пользовательские свойства](/api_help/iblock/classes/user_properties/index.php)

GetSettingsHTML (доступен с 8.6.1)

GetSettingsHTML
===============

Включить вкладки

Описание и параметры

Возвращаемое значение

Смотрите также

Примеры использования

### Описание и параметры

```
string
CIBlockProperty*::GetSettingsHTML(
	array arProperty,
	array strHTMLControlName,
	array &arPropertyFields
);Копировать
```

Метод возвращает безопасный HTML отображения настроек свойства для формы редактирования инфоблока. Метод статический при использовании штатных свойств. У свойств, созданных клиентом, обязан быть статическим при использовании php7.

**Примечание:** вызывается при построении формы редактирования инфоблока.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| arProperty | Метаданные свойства. См. [Свойства элементов инфоблока](/api_help/iblock/fields.php#fproperty) |
| strHTMLControlName | Имя элемента управления для заполнения настроек свойства. Массив вида:  ``` array( 	"NAME" => html безопасное имя для настроек, );Копировать ``` |
| arPropertyFields | Пустой массив. |

### Возвращаемое значение

HTML для встраивания в форму редактирования инфоблока.

В параметре arPropertyFields можно вернуть дополнительные флаги управления формой:
  

* HIDE - массив названий полей свойства которые будут скрыты для редактирования. Возможные значения: MULTIPLE, SEARCHABLE, FILTRABLE, WITH\_DESCRIPTION, MULTIPLE\_CNT, ROW\_COUNT, COL\_COUNT и DEFAULT\_VALUE.
* SHOW - массив полей которые должны быть показаны даже если базовое свойство их не поддерживает. Возможные значения: MULTIPLE, SEARCHABLE, FILTRABLE, WITH\_DESCRIPTION, MULTIPLE\_CNT, ROW\_COUNT и COL\_COUNT.
* SET - ассоциативный массив полей для принудительного выставления значений в случае если они не отображаются в форме. Возможные значения: MULTIPLE, SEARCHABLE, FILTRABLE, WITH\_DESCRIPTION, MULTIPLE\_CNT, ROW\_COUNT и COL\_COUNT.
* USER\_TYPE\_SETTINGS\_TITLE - строка для отображения в качестве заголовка секции настроек.

### Смотрите также

* [Свойства элементов инфоблока](/api_help/iblock/fields.php#fproperty)
* [GetUserTypeDescription](/api_help/iblock/classes/user_properties/GetUserTypeDescription.php)

### Примеры использования

```
<?
class CIBlockPropertyMyDateTime
{
	function GetSettingsHTML($arProperty, $strHTMLControlName, &$arPropertyFields)
	{
		$arPropertyFields = array(
			"HIDE" => array("FILTRABLE", "ROW_COUNT", "COL_COUNT", "DEFAULT_VALUE"), //will hide the field
			"SET" => array("FILTRABLE" => "N"), //if set then hidden field will get this value
			"USER_TYPE_SETTINGS_TITLE" => "Настройки даты/времени"
		);
		return '<tr>
		<td>Длина поля ввода:</td>
		<td><input type="text" size="5" name="'.$strHTMLControlName["NAME"].'[WIDTH]"></td>
		</tr>';
	}
}
?>Копировать
```

Новинки документации в соцсетях: