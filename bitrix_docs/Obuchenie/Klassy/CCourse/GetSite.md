[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CCourse](/api_help/learning/classes/ccourse/index.php)

GetSite (доступен с 5.0.3)

GetSite
=======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
CDBResult
CCourse::GetSite(
	int COURSE_ID
);Копировать
```

Возвращает список сайтов для учебного курса с идентификатором COURSE\_ID. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| COURSE\_ID | Идентификатор курса. |

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php).

#### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$ID = 106;//Course ID
	$arSite = Array();
	$db_SITE_ID = CCourse::GetSite($ID);
	while($ar_SITE_ID = $db_SITE_ID->Fetch())
		$arSite[] = $ar_SITE_ID["LID"];
}
?>Копировать
```

Новинки документации в соцсетях: