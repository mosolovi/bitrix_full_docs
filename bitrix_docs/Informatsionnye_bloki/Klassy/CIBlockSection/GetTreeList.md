[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockSection](/api_help/iblock/classes/ciblocksection/index.php)

GetTreeList (доступен с 3.0.4)

GetTreeList
===========

```
CDBResult
CIBlockSection::GetTreeList(
	array arFilter=Array(),
	array arSelect=Array()
);Копировать
```

Метод возвращает список разделов, отсортированный в порядке "полного развернутого дерева". Метод статический. По сути является оберткой метода [CIBlockSection](/api_help/iblock/classes/ciblocksection/index.php)::[GetList](/api_help/iblock/classes/ciblocksection/getlist.php)() с предустановленным параметром сортировки:

```
CIBlockSection::GetList(Array("left_margin"=>"asc"), $arFilter);Копировать
```

#### Смотрите также

* [CIBlockSection](/api_help/iblock/classes/ciblocksection/index.php)::[GetList](/api_help/iblock/classes/ciblocksection/getlist.php)

Новинки документации в соцсетях: