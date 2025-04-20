[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockPropertyEnum](/api_help/iblock/classes/ciblockpropertyenum/index.php)

GetList (доступен с 3.1.3)

GetList
=======

Включить вкладки

Описание

Параметры вызова

Примеры использования

### Описание

```
CDBResult CIBlockPropertyEnum::GetList(
	array arOrder = Array("SORT"=>"ASC", "VALUE"=>"ASC"),
	array arFilter = Array()
);Копировать
```

Возвращает список вариантов значений свойств типа "список" по фильтру *arFilter* отсортированные в порядке *arOrder*. Метод статический.

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php)

#### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)
* [Поля варианта значений свойства типа "список"](/api_help/iblock/fields.php#fproperty)

### Параметры вызова

| Параметр | Описание |
| --- | --- |
| arOrder | Массив для сортировки, имеющий вид *by1*=>*order1*[, *by2*=>*order2* [, ..]], где *by* - поле сортировки, может принимать значения:    * *id* - код варианта значения; * *value* - значение варианта; * *sort* - индекс сортировки варианта; * *xml\_id* или *external\_id* - внешний код варианта значения; * *def* - по признаку "значение по умолчанию"; * *property\_id* - код свойства; * *property\_sort* - индекс сортировки свойства; * *property\_code* - символьный код свойства;   *order* - порядок сортировки, может принимать значения:    * *asc* - по возрастанию; * *desc* - по убыванию; |
| arFilter | Массив вида array("фильтруемое поле"=>"значение" [, ...])   "фильтруемое поле" может принимать значения:    * *VALUE* - по значению (по шаблону [%\_]); * *ID* - по коду значения варианта свойства; * *SORT* - по индексу сортировки варианта свойства; * *DEF* - по параметру "значение по умолчанию" (Y|N); * *XML\_ID* - по внешнему коду(по шаблону [%\_]); * *EXTERNAL\_ID* - по внешнему коду; * *CODE* - по символьному коду свойства (по шаблону [%\_]); * *PROPERTY\_ID* - по числовому или символьному коду свойства; * *IBLOCK\_ID* - фильтр по коду информационного блока, которому принадлежит свойство;  Необязательное. По умолчанию записи не фильтруются. |

### Примеры использования

```
<?
$property_enums = CIBlockPropertyEnum::GetList(Array("DEF"=>"DESC", "SORT"=>"ASC"), Array("IBLOCK_ID"=>$IBLOCK_ID, "CODE"=>"COLORS"));
while($enum_fields = $property_enums->GetNext())
{
	echo $enum_fields["ID"]." - ".$enum_fields["VALUE"]."<br>";
}
?>Копировать
```

Новинки документации в соцсетях: