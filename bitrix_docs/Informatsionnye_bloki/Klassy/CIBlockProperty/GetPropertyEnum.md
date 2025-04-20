[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockProperty](/api_help/iblock/classes/ciblockproperty/index.php)

GetPropertyEnum (доступен с 3.1.3)

GetPropertyEnum
===============

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
CDBResult CIBlockProperty::GetPropertyEnum(
	mixed PROP_ID, 
	array arOrder = Array("SORT"=>"asc"), 
	array arFilter = Array()
)Копировать
```

Возвращает варианты для значения свойства *PROP\_ID* типа "список" отсортированные в порядке *arOrder* и отфильтрованные по *arFilter*. Метод статический.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| PROP\_ID | Числовой или символьный код свойства. |
| arOrder | Массив для сортировки, имеющий вид *by1*=>*order1*[, *by2*=>*order2* [, ..]], где *by* - поле сортировки, может принимать значения:       *id* - код;       *value* - значение,       *sort* - поле сортировки*,*    *external\_id* - внешний код,   *order* - порядок сортировки, может принимать значения:       *asc* - по возрастанию;       *desc* - по убыванию; |
| arFilter | Массив вида array("фильтруемое поле"=>"значение" [, ...])   "фильтруемое поле" может принимать значения:       *VALUE* - по значению варианта свойства (можно искать по шаблону [%\_]);       *EXTERNAL\_ID* - по значению внешнего кода варианта свойства (можно искать по шаблону [%\_]);       *IBLOCK\_ID* - по коду информационного блока, которому принадлежит свойство;       *ID* - по коду значения варианта свойства;   Необязательное. По умолчанию записи не фильтруются. |

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php), содержащий записи [полей вариантов свойства](/api_help/iblock/fields.php#fiblockpropertyenum).

### Смотрите также

* [Поля вариантов свойства](/api_help/iblock/fields.php#fiblockpropertyenum)
* [CIBlockPropertyEnum](/api_help/iblock/classes/ciblockpropertyenum/index.php)::[GetList()](/api_help/iblock/classes/ciblockpropertyenum/getlist.php)

### Примеры использования

```
<?
$db_enum_list = CIBlockProperty::GetPropertyEnum("IMPORTANT_NEWS", Array(), Array("IBLOCK_ID"=>$BID, "VALUE"=>"Yes"));
if($ar_enum_list = $db_enum_list->GetNext())
{
	$db_important_news = CIBlockElement::GetList(Array(), Array("IBLOCK_ID"=>$BID, "PROPERTY"=>array("IMPORTANT_NEWS"=>$ar_enum_list["ID"])));
}
?>Копировать
```

Новинки документации в соцсетях: