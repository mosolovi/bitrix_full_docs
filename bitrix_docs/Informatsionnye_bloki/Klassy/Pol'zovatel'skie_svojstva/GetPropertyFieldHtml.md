[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[Пользовательские свойства](/api_help/iblock/classes/user_properties/index.php)

GetPropertyFieldHtml (доступен с 5.1.0)

GetPropertyFieldHtml
====================

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
string
CIBlockProperty*::GetPropertyFieldHtml(
	array arProperty,
	array value,
	array strHTMLControlName
);Копировать
```

Метод должен вернуть HTML отображения элемента управления для редактирования значений свойства в административной части. Метод статический при использовании штатных свойств. У свойств, созданных клиентом, обязан быть статическим при использовании php7.

**Примечание:** вызывается во время построения формы редактирования элемента.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| arProperty | Метаданные свойства. См. [Свойства элементов инфоблока](/api_help/iblock/fields.php#fproperty) |
| value | Значение свойства. Массив вида:   array(   "VALUE" => значение,   "DESCRIPTION" => описание,   ); |
| strHTMLControlName | Имена элементов управления для заполнения значения свойства и его описания. Массив вида:   array(   "VALUE" => html безопасное имя для значения,   "DESCRIPTION" => html безопасное имя для описания,   "MODE" => может принимать зачение "FORM\_FILL" при вызове из формы редактирования элемента или "iblock\_element\_admin" при редактировании в режиме просмотра списка элементов, а также "EDIT\_FORM" при редактировании инфоблока.   "FORM\_NAME" => имя формы в которую будет встроен элемент управления.   ); |

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
	function GetPropertyFieldHtml($arProperty, $value, $strHTMLControlName)
	{
		return  CAdminCalendar::CalendarDate($strHTMLControlName["VALUE"], $value["VALUE"], 20).
			($arProperty["WITH_DESCRIPTION"]=="Y"?
				' <input type="text" size="20" name="'.$strHTMLControlName["DESCRIPTION"].'" value="'.htmlspecialchars($value["DESCRIPTION"]).'">'
				:''
			);
	}
}
?>Копировать
```

Новинки документации в соцсетях: