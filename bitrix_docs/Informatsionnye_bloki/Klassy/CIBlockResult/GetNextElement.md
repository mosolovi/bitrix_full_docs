[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockResult](/api_help/iblock/classes/ciblockresult/index.php)

GetNextElement (доступен с 3.1.3)

GetNextElement
==============

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
_CIBElement
CIBlockResult::GetNextElement(
	bool bTextHtmlAuto =  true,
	bool use_tilda =  true
);Копировать
```

Метод возвращает из выборки объект [\_CIBElement](/api_help/iblock/classes/_cibelement/index.php). Нестатический метод.

#### Параметры вызова

| Параметр | Описание | С версии |
| --- | --- | --- |
| $bTextHtmlAuto | Параметр передается в [CDBResult::GetNext](/api_help/main/reference/cdbresult/getnext.php). Необязательный, по умолчанию принимает *true*. | 7.1.1 |
| use\_tilda |

#### Возвращаемое значение

Метод возвращает из выборки объект [\_CIBElement](/api_help/iblock/classes/_cibelement/index.php), и передвигает курсор на следующую запись.  
Если достигнута последняя запись (или в результате нет ни одной записи), метод вернет false.

### Смотрите также

* [\_CIBElement](/api_help/iblock/classes/_cibelement/index.php)
* [CIBlockResult](/api_help/iblock/classes/ciblockresult/index.php)::[GetNext()](/api_help/iblock/classes/ciblockresult/getnext.php)
* [CIBlockElement](/api_help/iblock/classes/ciblockelement/index.php)::[GetList()](/api_help/iblock/classes/ciblockelement/getlist.php)

### Примеры использования

```
<?
$res = CIBlockElement::GetByID($_GET["PID"]);
if($obRes = $res->GetNextElement())
{
	$ar_res = $obRes->GetFields();
	echo $ar_res['NAME'];
}
?>Копировать
```

```
//выборка всех данных элемента: 
$db_elemens = CIblockElement::GetList($arOrder, $arFilter, false, false, $arSelect);
while($obElement = $db_elemens->GetNextElement())
{
	$el = $obElement->GetFields();
	$el["PROPERTIES"] = $obElement->GetProperties();
		$arResult["ITEMS"][] = $el;
}
//Примечание: в данном случае в $arSelect ничего задавать не нужно (можно его вообще не писать). Так как функции GetFields и GetProperties выбирает все свойства, которые есть у элемента.
//Этот способ нужно использовать для выборки элементов, у которых есть множественные свойства, чтобы избежать дублирования элементов, которое наблюдается при стандартном вызове GetNext.Копировать
```

Новинки документации в соцсетях: