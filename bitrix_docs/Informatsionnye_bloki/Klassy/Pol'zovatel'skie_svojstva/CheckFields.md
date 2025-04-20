[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[Пользовательские свойства](/api_help/iblock/classes/user_properties/index.php)

CheckFields (доступен с 5.1.0)

CheckFields
===========

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
array
CIBlockProperty*::CheckFields(
	array arProperty,
	array value
);Копировать
```

Метод должен проверить корректность значения свойства и вернуть массив. Пустой, если ошибок нет, и с сообщениями об ошибках, если есть. Метод статический.

**Примечание**: вызывается перед добавлением или изменением элемента.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| arProperty | Метаданные свойства. См. [Свойства элементов инфоблока](/api_help/iblock/fields.php#fproperty) |
| value | Значение свойства. Массив вида:  ``` array( 	"VALUE" => значение, );Копировать ``` |

#### Возвращаемое значение

Массив сообщений об ошибках или пустой массив.

### Смотрите также

* [Свойства элементов инфоблока](/api_help/iblock/fields.php#fproperty)
* [GetUserTypeDescription](/api_help/iblock/classes/user_properties/GetUserTypeDescription.php)

### Примеры использования

```
<?
class CIBlockPropertyMyDateTime
{
	function CheckFields($arProperty, $value)
	{
		$arResult = array();
		if(strlen($value["VALUE"])>0 && !CheckDateTime($value["VALUE"]))
			$arResult[] = GetMessage("IBLOCK_PROP_DATETIME_ERROR");
		return $arResult;
	}
}
?>Копировать
```

Новинки документации в соцсетях: