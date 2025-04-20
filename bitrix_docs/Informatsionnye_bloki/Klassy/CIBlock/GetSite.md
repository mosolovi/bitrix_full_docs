[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlock](/api_help/iblock/classes/ciblock/index.php)

GetSite (доступен с 3.3.8)

GetSite
=======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
CDBResult
CIBlock::GetSite(
	int iblock_id
);Копировать
```

Метод возвращает список сайтов к которым привязан инфоблок. Метод статический.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| iblock\_id | Идентификатор информационного блока. |

#### Возвращаемое значение

Возвращается объект [CDBResult.](/api_help/main/reference/cdbresult/index.php)

#### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)
* [Поля CSite](/api_help/main/reference/csite/index.php#flds)

### Примеры использования

```
<?
$SITES = '';
$rsSites = CIBlock::GetSite($IBLOCK_ID);
while($arSite = $rsSites->Fetch())
	$SITES .= ($SITES!=""?" / ":"").htmlspecialchars($arSite["SITE_ID"]);
?>Копировать
```

Новинки документации в соцсетях: