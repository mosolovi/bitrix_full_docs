[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[Пользовательские свойства](/api_help/iblock/classes/user_properties/index.php)

ConvertToDB (доступен с 5.1.0)

ConvertToDB
===========

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
array
CIBlockProperty*::ConvertToDB(
	array arProperty,
	array value
);Копировать
```

Метод должен преобразовать значение свойства в формат пригодный для сохранения в базе данных. И вернуть массив вида array("VALUE" => "...", "DESCRIPTION" => "..."). Если значение свойства это массив, то разумным будет использование функции serialize. А вот Дата/время преобразуется в ODBC формат "YYYY-MM-DD HH:MI:SS". Это определит возможности сортировки и фильтрации по значениям данного свойства. Метод статический при использовании штатных свойств. У свойств, созданных клиентом, обязан быть статическим при использовании php7.

**Примечание:** вызывается перед сохранением значения свойства в БД.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| arProperty | Метаданные свойства. См. [Свойства элементов инфоблока](/api_help/iblock/fields.php#fproperty) |
| value | Значение свойства. Массив вида:   array(   "VALUE" => значение,   "DESCRIPTION" => описание,   ); |

#### Возвращаемое значение

Строка представление для БД.

### Смотрите также

* [Свойства элементов инфоблока](/api_help/iblock/fields.php#fproperty)
* [GetUserTypeDescription](/api_help/iblock/classes/user_properties/GetUserTypeDescription.php)

### Примеры использования

```
<?
class CIBlockPropertyMyDateTime
{
	function ConvertToDB($arProperty, $value)
	{
		if(strlen($value["VALUE"])>0)
		{
			$value["VALUE"] = CDatabase::FormatDate(
				$value["VALUE"],
				CLang::GetDateFormat("FULL"), "YYYY-MM-DD HH:MI:SS"
			);
		}
		return $value;
	}
}
?>Копировать
```

Новинки документации в соцсетях: