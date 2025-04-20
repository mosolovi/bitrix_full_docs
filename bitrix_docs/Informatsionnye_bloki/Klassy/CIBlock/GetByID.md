[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlock](/api_help/iblock/classes/ciblock/index.php)

GetByID (доступен с 3.0.3)

GetByID
=======

```
CDBResult
CIBlock::GetByID(
	int ID
);Копировать
```

Возвращает информационный блок по его коду *ID*. Метод статический.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | Код информационного блока. |

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php).

#### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)
* [Поля результата](/api_help/iblock/fields.php#fiblock)

#### Примеры использования

```
<?
$res = CIBlock::GetByID($_GET["BID"]);
if($ar_res = $res->GetNext())
	echo $ar_res['NAME'];
?>Копировать
```

Новинки документации в соцсетях: