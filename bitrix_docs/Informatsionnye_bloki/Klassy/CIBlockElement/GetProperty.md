[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockElement](/api_help/iblock/classes/ciblockelement/index.php)

GetProperty (доступен с 3.0.8)

GetProperty
===========

Включить вкладки

Описание

Параметры вызова

Возвращаемое значение

Примеры использования

### Описание

```
CDBResult
	CIBlockElement::GetProperty(
	int iblock_id,
	int element_id,
	array arOrder = Array(),
	array arFilter = Array()
);Копировать
```

Метод возвращает значения свойства для элемента *element\_id*. Метод статический.

#### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)
* [Поля свойств](/api_help/iblock/fields.php#fproperty)

### Параметры вызова

| Параметр | Описание |
| --- | --- |
| iblock\_id | Код инфоблока. |
| element\_id | Код элемента. |
| arOrder | Массив вида Array(*by1*=>*order1*[, *by2*=>*order2* [, ..]]), где *by* - поле для сортировки, может принимать значения:  * **id** - код свойства; * **sort** - индекс сортировки; * **name** - имя свойства; * active - активность свойства; * value\_id - код значения свойства; * enum\_sort - индекс сортировки варианта списочного свойства;  *order* - порядок сортировки, может принимать значения:  * **asc** - по возрастанию; * **desc** - по убыванию;  Необязательный. По умолчанию равен *Array("sort"=>"asc")*  **Примечание:** параметр не должен быть *false*, иначе метод отработает неправильно и результат не будет отобран по заданным критериям. |
| arFilter | Массив вида array("фильтруемое поле"=>"значения фильтра" [, ...]) "фильтруемое поле" может принимать значения: ACTIVE - активность (Y/N),    * NAME - название свойства (можно использовать маску %|\_), * ID - код свойства, * ACTIVE - активность (Y|N), * SEARCHABLE - участвует в поиске или нет (Y|N), * PROPERTY\_TYPE - тип свойства, * CODE - символьный код свойства, * EMPTY - пустота свойства (Y|N).  Не обязательный параметр, по умолчанию равен array(). |

**Примечание** - Существуют ещё параметры, оставленные для сохранения совместимости: **$by** и **$order** .

### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php), содержащий [поля свойств](/api_help/iblock/fields.php#fproperty) и поля со значениями:

  
PROPERTY\_VALUE\_ID - код значения свойства,
  
VALUE - значение свойства,
  
DESCRIPTION - описание значения свойства,
  
VALUE\_ENUM - текстовое значение элемента списочного свойства,
  
VALUE\_XML\_ID - внешний код значения свойства типа "список".

### Примеры использования

Пример 1:

```
<?
$db_props = CIBlockElement::GetProperty($PRODUCT_IBLOCK_ID, $PRODUCT_ID, array("sort" => "asc"), Array("CODE"=>"FORUM_TOPIC_ID"));
if($ar_props = $db_props->Fetch())
	$FORUM_TOPIC_ID = IntVal($ar_props["VALUE"]);
else
	$FORUM_TOPIC_ID = false;
?>Копировать
```

Пример 2 (получить значения для множественного свойства):

```
$VALUES = array();
$res = CIBlockElement::GetProperty(IKSO_CUSTOM::$IBLOCKS['brands'], $BRAND_ID, "sort", "asc", array("CODE" => "BRAND_CLASS"));
while ($ob = $res->GetNext())
{
	$VALUES[] = $ob['VALUE'];
}Копировать
```

Пример 3 (получить значения для немножественного свойства):

```
$res = CIBlockElement::GetProperty(IKSO_CUSTOM::$IBLOCKS['brands'], $BRAND_ID, "sort", "asc", array("CODE" => "BRAND_CLASS"));
	if ($ob = $res->GetNext())
	{
		$VALUE = $ob['VALUE'];
	}Копировать
```

Пример 4:

Если значений у свойства нет и в фильтр не передается "EMPTY"=>"N", то метод вернет массив с с пустым ключом VALUE:

```
//используются Инфоблоки 2.0
$db_props = CIBlockElement::GetProperty(30, 14391, "sort", "asc", Array("CODE"=>"XXX")); // XXX - множественное свойства типа "Строка"
if($ar_props = $db_props->Fetch()):
echo "<pre>".print_r($ar_props, true)."<pre>";
endif;Копировать
```

Пример 5

Если нужно получить имена значения типа список

```
?
$res = CIBlockElement::GetProperty(ID_BLOKA, ID_ELEMENTA, array("sort" => "asc"), Array("CODE"=>"CATEGORIES"));
	while ($ob = $res->GetNext()) {
		$prop = $ob['VALUE_ENUM'];
		echo $prop. "
";    
	}
?Копировать
```

Новинки документации в соцсетях: