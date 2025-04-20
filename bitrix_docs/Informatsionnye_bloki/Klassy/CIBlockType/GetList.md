[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockType](/api_help/iblock/classes/ciblocktype/index.php)

GetList (доступен с 3.1.3)

GetList
=======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
CDBResult
CIBlockType::GetList(
	array arOrder = Array("SORT"=>"ASC"),
	array arFilter = Array()
);Копировать
```

Возвращает список типов информационных блоков по фильтру *arFilter* с сортировкой *arOrder*. Метод статический.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| arOrder | Массив полей для сортировки, содержащий пары "поле сортировки"=>"направление сортировки".   Поля сортировки могут принимать значения:      *id* - код типа;      *sort* - индекс сортировки;      *NAME* - название типа. |
| arFilter | Массив вида array("фильтруемое поле"=>"значение" [, ...])   может принимать значения:      *ID* - регистронезависимый по подстроке в коде типа;      *=ID* - точное совпадение с кодом типа;      *NAME* - регистронезависимый по подстроке в названии типа (для всех языков);   Необязательное. По умолчанию записи не фильтруются.      *LANGUAGE\_ID* - код языка. |

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php)

### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)
* [Поля CIBlockType](/api_help/iblock/fields.php#fiblocktype)

### Примеры использования

```
<?
$db_iblock_type = CIBlockType::GetList();
while($ar_iblock_type = $db_iblock_type->Fetch())
{
	if($arIBType = CIBlockType::GetByIDLang($ar_iblock_type["ID"], LANG))
	{
		echo htmlspecialcharsEx($arIBType["NAME"])."<br>";
	}   
}
?>Копировать
```

Новинки документации в соцсетях: