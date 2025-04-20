[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[Пользовательские свойства](/api_help/iblock/classes/user_properties/index.php)

GetUserTypeDescription (доступен с 5.1.0)

GetUserTypeDescription
======================

Включить вкладки

Описание

Структура массива

Смотрите также

Примеры использования

### Описание

```
array
CIBlockProperty*::GetUserTypeDescription(
);Копировать
```

Метод возвращает массив описывающий поведение пользовательского свойства. Вызывается по событию [OnIBlockPropertyBuildList](/api_help/iblock/events/OnIBlockPropertyBuildList.php). Метод статический при использовании штатных свойств. У свойств, созданных клиентом, обязан быть статическим при использовании php7.

#### Параметры вызова

Отсутствуют.
  

#### Возвращаемое значение

Массив.

### Структура массива

| Поле | Описание |
| --- | --- |
| PROPERTY\_TYPE | Обязательное. Указывает модулю какое свойство будет базовым для хранения значений пользовательского свойства, а также для фильтрации и некоторых других действий. Возможные значения:    * S - строка * N - число с плавающей точкой * L - список значений * F - файл * G - привязка к разделам * E - привязка к элементам |
| USER\_TYPE | Обязательное. Уникальный идентификатор пользовательского свойства. |
| DESCRIPTION | Обязательное. Краткое описание. Будет выведено в списке выбора типа свойства при редактировании информационного блока. |
| [CheckFields](/api_help/iblock/classes/user_properties/CheckFields.php) | Не обязательное. Значением этого поля должен быть массив из двух элементов. В первом должно быть название класса, а во втором название метода который будет вызван при наступлении соответствующего события. |
| [GetUIFilterProperty](/api_help/iblock/classes/user_properties/getuifilterproperty.php) | Аналогично. С версии 18.5.0. |
| [GetLength](/api_help/iblock/classes/user_properties/GetLength.php) | Аналогично. |
| [ConvertToDB](/api_help/iblock/classes/user_properties/ConvertToDB.php) | Аналогично. |
| [ConvertFromDB](/api_help/iblock/classes/user_properties/ConvertFromDB.php) | Аналогично. |
| [GetPropertyFieldHtml](/api_help/iblock/classes/user_properties/GetPropertyFieldHtml.php) | Аналогично. |
| [GetPropertyFieldHtmlMulty](/api_help/iblock/classes/user_properties/getpropertyfieldhtmlmulty.php) | Необязательный обработчик. Является аналогом [GetPropertyFieldHtml](/api_help/iblock/classes/user_properties/GetPropertyFieldHtml.php) за исключением того, что в *value* приходят несколько значений.. |
| [GetAdminListViewHTML](/api_help/iblock/classes/user_properties/GetAdminListViewHTML.php) | Аналогично. |
| [GetPublicViewHTML](/api_help/iblock/classes/user_properties/GetPublicViewHTML.php) | Аналогично. |
| [GetPublicEditHTML](/api_help/iblock/classes/user_properties/GetPublicEditHTML.php) | Аналогично. |
| [GetSettingsHTML](/api_help/iblock/classes/user_properties/GetSettingsHTML.php) | Аналогично. |
| [PrepareSettings](/api_help/iblock/classes/user_properties/PrepareSettings.php) | Аналогично. |

### Смотрите также

* [OnIBlockPropertyBuildList](/api_help/iblock/events/OnIBlockPropertyBuildList.php)

### Примеры использования

```
<?
class CIBlockPropertyMyDateTime
{
	public static function GetUserTypeDescription()
	{
		return array(
			"PROPERTY_TYPE"		=>"S",
			"USER_TYPE"		=>"MyDateTime",
			"DESCRIPTION"		=>"Дата/Время",
			//optional handlers
			"CheckFields"		=>array("CIBlockPropertyMyDateTime","CheckFields"),
			"GetLength"		=>array("CIBlockPropertyMyDateTime","GetLength"),
			"ConvertToDB"		=>array("CIBlockPropertyMyDateTime","ConvertToDB"),
			"ConvertFromDB"		=>array("CIBlockPropertyMyDateTime","ConvertFromDB"),
			"GetPropertyFieldHtml"	=>array("CIBlockPropertyMyDateTime","GetPropertyFieldHtml"),
			"GetAdminListViewHTML"	=>array("CIBlockPropertyMyDateTime","GetAdminListViewHTML"),
			"GetPublicViewHTML"	=>array("CIBlockPropertyMyDateTime","GetPublicViewHTML"),
			"GetPublicEditHTML"	=>array("CIBlockPropertyMyDateTime","GetPublicEditHTML"),
		);
	}
}
?>Копировать
```

Новинки документации в соцсетях: