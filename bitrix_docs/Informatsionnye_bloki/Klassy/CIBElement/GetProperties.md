[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[\_CIBElement](/api_help/iblock/classes/_cibelement/index.php)

GetProperties (доступен с 3.1.3)

GetProperties
=============

Включить вкладки

Описание

Параметры вызова

Возвращаемое значение

Примеры использования

### Описание

```
array
_CIBElement::GetProperties(
	arOrder = false, 
	arFilter = Array()
);Копировать
```

Метод возвращает значения свойств текущего элемента информационного блока. Нестатический метод.

**Примечание:** данный метод не работает, если в [CIBlockElement::GetList](/api_help/iblock/classes/ciblockelement/getlist.php) в **arSelectFields** не указаны *ID* и *IBLOCK\_ID*, а в **arFilter** не задан *IBLOCK\_ID*. Должно быть, например, так:

```
$dbEl = CIBlockElement::GetList(
	Array(), 
	Array("IBLOCK_TYPE"=>"catalog", "IBLOCK_ID"=>11), 
	false, 
	false, 
	array("ID" , "IBLOCK_ID", ......)
);Копировать
```

#### Смотрите также

* [\_CIBElement](/api_help/iblock/classes/_cibelement/index.php)::[GetProperties()](/api_help/iblock/classes/_cibelement/getproperties.php)
* [CIBlockElement](/api_help/iblock/classes/ciblockelement/index.php)::[GetProperty()](/api_help/iblock/classes/ciblockelement/getproperty.php)

### Параметры вызова

| Параметр | Описание |
| --- | --- |
| *arOrder* | Массив вида Array(*by1*=>*order1*[, *by2*=>*order2* [, ..]]), где *by* - поле для сортировки, может принимать значения:  * **id** - код свойства; * **sort** - индекс сортировки; * **name** - имя свойства; * active - активность свойства; * value\_id - код значения свойства; * enum\_sort - индекс сортировки варианта списочного свойства;  *order* - порядок сортировки, может принимать значения:  * **asc** - по возрастанию; * **desc** - по убыванию; |
| *arFilter* | Массив вида array("фильтруемое поле"=>"значения фильтра" [, ...])   "фильтруемое поле" может принимать значения:       *NAME* - название свойства;       *ID* - код свойства;       *ACTIVE* - активность свойства (Y|N), по умолчанию выводятся только активные свойства, если необходимо вывести все значения, то установите *ACTIVE* в пустое значение;       *SEARCHABLE* - участвует в поиске или нет (Y|N);       *PROPERTY\_TYPE* - тип свойства;       *CODE* - символьный код свойства;       *EMPTY* - пустота значения свойства (Y|N). По умолчанию выводятся все свойства и имеющие непустые значения и без значений.   Не обязательный параметр, по умолчанию равен array(). |

### Возвращаемое значение

Метод возвращает массив значений свойств, где:

* в качестве индексов массива "Символьный код свойства" (задается в настройках информационного блока) или, если символьный код свойства не указан, то уникальный числовой ID свойства.
* значением массива будет массив полей свойства и дополнительно поля со значениями свойства:   
  *VALUE* - значение свойства или массив значений свойств, если свойство множественное,   
  *VALUE\_ENUM\_ID* - код варианта значения для свойства типа "Список" (массив или единичное значение),   
  *VALUE\_XML\_ID* - внешний код варианта значения для свойства типа "Список" (массив или единичное значение),   
  *DESCRIPTION* - описание значения свойства (массив или единичное значение),   
  *PROPERTY\_VALUE\_ID* - код значения свойства (массив или единичное значение)

### Примеры использования

```
<?
include($_SERVER['DOCUMENT_ROOT'].'/bitrix/header.php');
if(CModule::IncludeModule('iblock'))
{
	$dbEl = CIBlockElement::GetList(Array(), Array("IBLOCK_TYPE"=>"catalog", "IBLOCK_ID"=>11));
	if($obEl = $dbEl->GetNextElement())
	{   
		$props = $obEl->GetProperties();
		echo "<pre>";
		print_r($props);
		echo "</pre>";
	}
}
?>
<?include($_SERVER['DOCUMENT_ROOT'].'/bitrix/footer.php');?>Копировать
```

```
Вывод примера:
Array
(
	[27] => Array
	(
		[ID] => 27
		[TIMESTAMP_X] => 20041222191551
		[IBLOCK_ID] => 11
		[NAME] => Battery
		[ACTIVE] => Y
		[SORT] => 500
		[CODE] => 
		[DEFAULT_VALUE] => 
		[PROPERTY_TYPE] => L
		[ROW_COUNT] => 1
		[COL_COUNT] => 30
		[LIST_TYPE] => L
		[MULTIPLE] => Y
		[XML_ID] => 
		[FILE_TYPE] => 
		[MULTIPLE_CNT] => 5
		[TMP_ID] => 
		[WITH_DESCRIPTION] => 
		[LINK_IBLOCK_ID] => 0
		[VALUE_TYPE] => text
		[VALUE_ENUM] => Li-Mon
		[VALUE] => Array
		(
			[0] => Li-Test
			[1] => Li-NEW
			[2] => Li-Mon
		)
		[~VALUE] => Array
		(
			[0] => Li-Test
			[1] => Li-NEW
			[2] => Li-Mon
		)
		[DESCRIPTION] => Array
		(
			[0] => 
			[1] => 
			[2] => 
		)
		[~DESCRIPTION] => Array
		(
			[0] => 
			[1] => 
			[2] => 
		)
		[PROPERTY_VALUE_ID] => Array
		(
			[0] => 53860
			[1] => 53861
			[2] => 53862
		)
		[VALUE_ENUM_ID] => Array
		(
			[0] => 18
			[1] => 19
			[2] => 20
		)
		[~NAME] => Battery
		[~DEFAULT_VALUE] => 
	)
	[28] => Array
        (
		[ID] => 28
		[TIMESTAMP_X] => 20041222191551
		[IBLOCK_ID] => 11
		[NAME] => Screen
		[ACTIVE] => Y
		[SORT] => 500
		[CODE] => 
		[DEFAULT_VALUE] => 
		[PROPERTY_TYPE] => S
		[ROW_COUNT] => 1
		[COL_COUNT] => 30
		[LIST_TYPE] => L
		[MULTIPLE] => Y
		[XML_ID] => 
		[FILE_TYPE] => 
		[MULTIPLE_CNT] => 5
		[TMP_ID] => 
		[WITH_DESCRIPTION] => 
		[LINK_IBLOCK_ID] => 0
		[VALUE_TYPE] => 
		[VALUE_ENUM] => 
		[VALUE] => Color
		[~VALUE] => Color
		[DESCRIPTION] => 
		[~DESCRIPTION] => 
		[PROPERTY_VALUE_ID] => 32862
		[~NAME] => Screen
		[~DEFAULT_VALUE] => 
	)
	[29] => Array
	(
		[ID] => 29
		[TIMESTAMP_X] => 20041222191551
		[IBLOCK_ID] => 11
		[NAME] => PropertyX
		[ACTIVE] => Y
		[SORT] => 500
		[CODE] => 
		[DEFAULT_VALUE] => 
		[PROPERTY_TYPE] => N
		[ROW_COUNT] => 1
		[COL_COUNT] => 30
		[LIST_TYPE] => L
		[MULTIPLE] => Y
		[XML_ID] => 
		[FILE_TYPE] => 
		[MULTIPLE_CNT] => 5
		[TMP_ID] => 
		[WITH_DESCRIPTION] => 
		[LINK_IBLOCK_ID] => 0
		[VALUE_TYPE] => 
		[VALUE_ENUM] => 
		[VALUE] => 
		[~VALUE] => 
		[DESCRIPTION] => 
		[~DESCRIPTION] => 
		[PROPERTY_VALUE_ID] => 
		[~NAME] => PropertyX
		[~DEFAULT_VALUE] => 
	)
	[FORUM_TOPIC_ID] => Array
	(
		[ID] => 383
		[TIMESTAMP_X] => 20041223132810
		[IBLOCK_ID] => 11
		[NAME] => FORUM_TOPIC_ID
		[ACTIVE] => Y
		[SORT] => 500
		[CODE] => FORUM_TOPIC_ID
		[DEFAULT_VALUE] => 
		[PROPERTY_TYPE] => N
		[ROW_COUNT] => 1
		[COL_COUNT] => 30
		[LIST_TYPE] => L
		[MULTIPLE] => N
		[XML_ID] => 
		[FILE_TYPE] => 
		[MULTIPLE_CNT] => 5
		[TMP_ID] => 
		[WITH_DESCRIPTION] => 
		[LINK_IBLOCK_ID] => 0
		[VALUE_TYPE] => 
		[VALUE_ENUM] => 
		[VALUE] => 
		[~VALUE] => 
		[DESCRIPTION] => 
		[~DESCRIPTION] => 
		[PROPERTY_VALUE_ID] => 
		[~NAME] => FORUM_TOPIC_ID
		[~DEFAULT_VALUE] => 
	)
	[386] => Array
	(
		[ID] => 386
		[TIMESTAMP_X] => 20050119162457
		[IBLOCK_ID] => 11
		[NAME] => Photo
		[ACTIVE] => Y
		[SORT] => 500
		[CODE] => 
		[DEFAULT_VALUE] => 
		[PROPERTY_TYPE] => F
		[ROW_COUNT] => 1
		[COL_COUNT] => 30
		[LIST_TYPE] => L
		[MULTIPLE] => N
		[XML_ID] => 
		[FILE_TYPE] => 
		[MULTIPLE_CNT] => 5
		[TMP_ID] => 
		[WITH_DESCRIPTION] => Y
		[LINK_IBLOCK_ID] => 0
		[VALUE_TYPE] => text
		[VALUE_ENUM] => 
		[VALUE] => 2309
		[~VALUE] => 2309
		[DESCRIPTION] => HP
		[~DESCRIPTION] => HP 
		[PROPERTY_VALUE_ID] => 53863
		[~NAME] => Photo
		[~DEFAULT_VALUE] => 
	)
)Копировать
```

Новинки документации в соцсетях: