[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlock](/api_help/iblock/classes/ciblock/index.php)

GetProperties (доступен с 3.0.3)

GetProperties
=============

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
CDBResult CIBlock::GetProperties(
	int iblock_id, 
	array arOrder=Array(), 
	array arFilter=Array()
);Копировать
```

Возвращает свойства информационного блока *iblock\_id* с возможностью сортировки и дополнительной фильтрации. Нестатический метод.
  

**Примечание:** по умолчанию метод учитывает права доступа к информационному блоку. Для отключения проверки необходимо в параметре arFilter передать ключ "CHECK\_PERMISSIONS" со значением "N".

  

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| iblock\_id | Код информационного блока. |
| arOrder | Массив для сортировки результата. Содержит пары "поле сортировки"=>"направление сортировки". Поля сортировки см. [CIBlockProperty](/api_help/iblock/classes/ciblockproperty/index.php)::[GetList()](/api_help/iblock/classes/ciblockproperty/getlist.php). |
| arFilter | Массив вида array("фильтруемое поле"=>"значение фильтра" [, ...]). Фильтруемые поля и их значения смотрите в [CIBlockProperty](/api_help/iblock/classes/ciblockproperty/index.php)::[GetList()](/api_help/iblock/classes/ciblockproperty/getlist.php). |

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php)

### Смотрите также

* [Поля свойств](/api_help/iblock/fields.php#fproperty)
* [CIBlockProperty](/api_help/iblock/classes/ciblockproperty/index.php)::[GetList()](/api_help/iblock/classes/ciblockproperty/getlist.php)

### Примеры использования

```
<?
$res = CIBlock::GetProperties($IBLOCK_ID, Array(), Array("CODE"=>"SRC"));
if($res_arr = $res->Fetch())
	$SrcPropID = $res_arr["ID"];
else
{
	$arFields = Array(
		"NAME" 			=> "Источник импорта",
		"ACTIVE" 		=> "Y",
		"SORT" 			=> "1000",
		"DEFAULT_VALUE" => "",
		"CODE" 			=> "SRC",
		"ROW_COUNT" 	=> "1",
		"COL_COUNT" 	=> "10",
		"MULTIPLE"	 	=> "N",
		"MULTIPLE_CNT" 	=> "",
		"PROPERTY_TYPE"	=> "S",
		"LIST_TYPE" 	=> "L",
		"IBLOCK_ID" 	=> $IBLOCK_ID
		);
	$ibp = new CIBlockProperty;
	$SrcPropID = $ibp->Add($arFields);
	if(IntVal($SrcPropID)<=0)
		$strWarning .= $ibp->LAST_ERROR."<br>";
}
?>Копировать
```

Новинки документации в соцсетях: