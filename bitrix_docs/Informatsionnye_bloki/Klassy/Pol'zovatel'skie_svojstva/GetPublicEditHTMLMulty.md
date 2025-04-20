[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[Пользовательские свойства](/api_help/iblock/classes/user_properties/index.php)

GetPublicEditHTMLMulty (с версии 7.1.4)

GetPublicEditHTMLMulty
======================

Включить вкладки

Описание и параметры

Смотрите также

### Описание и параметры

```
string
CIBlockProperty*::GetPublicEditHTMLMulty(
	array arProperty,
	array value,
	array strHTMLControlName
);Копировать
```

Аналог [GetPublicEditHTML](/api_help/iblock/classes/user_properties/GetPublicEditHTML.php), но работает с множественными свойствами. Метод должен вернуть HTML отображения элемента управления для редактирования значений свойства в публичной части сайта. Метод статический при использовании штатных свойств. У свойств, созданных клиентом, обязан быть статическим при использовании php7.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| arProperty | Метаданные свойства. См. [Свойства элементов инфоблока](/api_help/iblock/fields.php#fproperty) |
| value | Значение свойства. Массив вида:   array(   "VALUE" => значение,   "DESCRIPTION" => описание,   ); |
| strHTMLControlName | Имена элементов управления для заполнения значения свойства и его описания. Массив вида:   array(   "VALUE" => html безопасное имя для значения,   "DESCRIPTION" => html безопасное имя для описания,   "FORM\_NAME" => имя формы в которую будет встроен элемент управления.   ); |

#### Возвращаемое значение

Строка.

### Смотрите также

* [Свойства элементов инфоблока](/api_help/iblock/fields.php#fproperty)
* [GetUserTypeDescription](/api_help/iblock/classes/user_properties/GetUserTypeDescription.php)

Новинки документации в соцсетях: