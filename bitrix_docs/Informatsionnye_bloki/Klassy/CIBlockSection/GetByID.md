[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockSection](/api_help/iblock/classes/ciblocksection/index.php)

GetByID (доступен с 3.0.4)

GetByID
=======

```
CIBlockResult
CIBlockSection::GetByID(
	int ID
);Копировать
```

Возвращает параметры раздела по его коду *ID*. Метод статический.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | Код раздела. |

#### Возвращаемое значение

Возвращается объект [CIBlockResult](/api_help/iblock/classes/ciblockresult/index.php). Пользовательские поля не возвращаются.

#### Смотрите также

* [CIBlockResult](/api_help/iblock/classes/ciblockresult/index.php)
* [Поля раздела](/api_help/iblock/fields.php#fsection)

#### Примеры использования

```
<?
$res = CIBlockSection::GetByID($_GET["GID"]);
if($ar_res = $res->GetNext())
	echo $ar_res['NAME'];
?>Копировать
```

Новинки документации в соцсетях: