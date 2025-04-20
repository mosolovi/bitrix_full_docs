[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[\_CIBElement](/api_help/iblock/classes/_cibelement/index.php)

GetGroups (доступен с 3.1.3)

GetGroups
=========

```
CDBResult
_CIBElement::GetGroups();Копировать
```

Возвращает группы, которым принадлежит текущий элемент и значения свойств типа "привязка к разделам" заданные для данного элемента. Нестатический метод.

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php) с полями разделов.

#### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)
* [CIBlockElement::GetElementGroups](/api_help/iblock/classes/ciblockelement/getelementgroups.php)

#### Примеры использования

```
<?
$res = CIBlockElement::GetByID($_GET["PID"]);
if($obRes = $res->GetNextElement())
{
	$ar_res = $obRes->GetGroups();
	print_r($ar_res);
}
?>Копировать
```

Новинки документации в соцсетях: