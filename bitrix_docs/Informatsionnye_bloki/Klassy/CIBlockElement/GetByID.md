[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockElement](/api_help/iblock/classes/ciblockelement/index.php)

GetByID (доступен с 3.0.8)

GetByID
=======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
CIBlockResult CIBlockElement::GetByID(
	int ID
);Копировать
```

Возвращается объект [CIBlockResult](/api_help/iblock/classes/ciblockresult/index.php) с [полями элемента информационного блока](/api_help/iblock/fields.php#felement). Метод статический.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | ID элемента. |

**Примечание:** метод не проверяет, чтобы элемент с кодом *ID* был опубликован и не являлся записью из истории. Для выборки только опубликованных элементов воспользуйтесь методом [CIBlockElement](/api_help/iblock/classes/ciblockresult/index.php)::[GetList()](/api_help/iblock/classes/ciblockelement/getlist.php).

#### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)
* [CIBlockResult](/api_help/iblock/classes/ciblockresult/index.php)
* [Поля элемента информационного блока](/api_help/iblock/fields.php#felement)
* [CIBlockElement](/api_help/iblock/classes/ciblockelement/index.php)::[GetList()](/api_help/iblock/classes/ciblockelement/getlist.php)

### Примеры использования

```
if(!CModule::IncludeModule("iblock"))
return; 
<?
$res = CIBlockElement::GetByID($_GET["PID"]);
if($ar_res = $res->GetNext())
	echo $ar_res['NAME'];
?>Копировать
```

Новинки документации в соцсетях: