[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[\_CIBElement](/api_help/iblock/classes/_cibelement/index.php)

GetProperty (доступен с 3.1.3)

GetProperty
===========

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
array
_CIBElement::GetProperty(
	mixed ID
);Копировать
```

Метод возвращает параметры свойства *ID* и его значения для текущего элемента информационного блока. Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| *ID* | Числовой или символьный код свойства. |

#### Возвращаемое значение

Метод возвращает массив [полей свойства](/api_help/iblock/fields.php#fproperty) и дополнительно поля со значениями свойства:   
    *VALUE* => значение свойства или массив значений свойств, если свойство множественное,  
    *VALUE\_ENUM\_ID* => код варианта значения для свойства типа "Список" (массив или единичное значение),  
    *DESCRIPTION* => описание значения свойства (массив или единичное значение),  
    *PROPERTY\_VALUE\_ID* => код значения свойства (массив или единичное значение).  

**Примечание:** если **GetProperty** применяется к результату работы [CIBlockElement::GetList](/api_help/iblock/classes/ciblockelement/getlist.php), то в **arSelectFields** необходимо **обязательно** указать *IBLOCK\_ID*, иначе результат будет пустым.

### Смотрите также

* [CIBlockElement](/api_help/iblock/classes/ciblockelement/index.php)::[GetProperty()](/api_help/iblock/classes/ciblockelement/getproperty.php)
* [\_CIBElement](/api_help/iblock/classes/_cibelement/index.php)::[GetProperties()](/api_help/iblock/classes/_cibelement/getproperties.php)

### Примеры использования

```
<?
$res = CIBlockElement::GetByID($_GET["PID"]);
if($obRes = $res->GetNextElement())
{
	$ar_res = $obRes->GetProperty("PHOTOS");
	print_r($ar_res);
}
?>Копировать
```

```
Вывод примера:

Array
(
	[ID] => 388
	[TIMESTAMP_X] => 20050119162457
	[IBLOCK_ID] => 11
	[NAME] => Photos with description
	[ACTIVE] => Y
	[SORT] => 500
	[CODE] => 
	[DEFAULT_VALUE] => 
	[PROPERTY_TYPE] => F
	[ROW_COUNT] => 1
	[COL_COUNT] => 30
	[LIST_TYPE] => L
	[MULTIPLE] => Y
	[XML_ID] => 
	[FILE_TYPE] => 
	[MULTIPLE_CNT] => 5
	[TMP_ID] => 
	[WITH_DESCRIPTION] => Y
	[LINK_IBLOCK_ID] => 0
	[VALUE_TYPE] => text
	[VALUE_ENUM] => 
	[VALUE] => Array
	(
		[0] => 2311
	)
	[~VALUE] => Array
	(
		[0] => 2311
	)
	[DESCRIPTION] => Array
	(
		[0] => Descr
	)
	[~DESCRIPTION] => Array
	(
		[0] => Descr
	)
	[PROPERTY_VALUE_ID] => Array
	(
		[0] => 53865
	)
	[~NAME] => Photos with description
	[~DEFAULT_VALUE] => 
)Копировать
```

Новинки документации в соцсетях: