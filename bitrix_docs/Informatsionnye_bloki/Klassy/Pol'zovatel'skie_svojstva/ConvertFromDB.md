[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[Пользовательские свойства](/api_help/iblock/classes/user_properties/index.php)

ConvertFromDB (доступен с 5.1.0)

ConvertFromDB
=============

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
array
CIBlockProperty*::ConvertFromDB(
	array arProperty,
	array value
);Копировать
```

Метод должен преобразовать значение свойства из формата пригодного для сохранения в базе данных в формат обработки. И вернуть массив вида array("VALUE" => "...", "DESCRIPTION" => "..."). Дополняет [ConvertToDB](/api_help/iblock/classes/user_properties/ConvertToDB.php). Метод статический при использовании штатных свойств. У свойств, созданных клиентом, обязан быть статическим при использовании php7.

**Примечание**: Вызывается в методе [CIBlockResult::Fetch](/api_help/iblock/classes/ciblockresult/getnext.php). Для корректной работы необходимо в фильтре метода [CIBlockElement::GetList](/api_help/iblock/classes/ciblockelement/getlist.php) указать "IBLOCK\_ID".

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| arProperty | Метаданные свойства. См. [Свойства элементов инфоблока](/api_help/iblock/fields.php#fproperty) |
| value | Значение свойства прочитанное из базы данных. Массив вида:   array(   "VALUE" => значение,   "DESCRIPTION" => описание,   ); |

#### Возвращаемое значение

Внешнее представление значения свойства.

### Смотрите также

* [Свойства элементов инфоблока](/api_help/iblock/fields.php#fproperty)
* [GetUserTypeDescription](/api_help/iblock/classes/user_properties/GetUserTypeDescription.php)
* [ConvertToDB](/api_help/iblock/classes/user_properties/ConvertToDB.php)

### Примеры использования

```
<?
class CIBlockPropertyMyDateTime
{
	function ConvertFromDB($arProperty, $value)
	{
		if(strlen($value["VALUE"])>0)
		{
			$value["VALUE"] = CDatabase::FormatDate(
				$value["VALUE"],
				"YYYY-MM-DD HH:MI:SS",
				CLang::GetDateFormat("FULL")
			);
			//Удалим незначимые нули
			$value["VALUE"] = str_replace(" 00:00:00", "", $value["VALUE"]);
		}
		return $value;
	}
}
?>Копировать
```

Новинки документации в соцсетях: