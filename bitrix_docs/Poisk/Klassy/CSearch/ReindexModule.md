[Поиск](/api_help/search/index.php)

[Классы](/api_help/search/classes/index.php)

[CSearch](/api_help/search/classes/csearch/index.php)

ReindexModule (доступен с 3.0.4)

ReindexModule
=============

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
void
CSearch::ReindexModule(
	string MODULE_ID,
	bool bFull = false
);Копировать
```

Метод инициирует переиндексацию указанного модуля. Для того, чтобы модуль был переиндексирован, он должен предоставить соответствующий метод, который должен быть зарегистрирован в системе событий как обработчик события [OnReIndex](/api_help/search/events/onreindex.php) модуля "search". Метод статический.

С помощью этого метода невозможно переиндексировать данные модуля "main". Т.к. индексация файлов выполняется не через обработчики событий, а непосредственно модулем поиска. Но можно воспользоваться методом [CSearch::ReIndexAll](/api_help/search/classes/csearch/reindexall.php), передав на первом шаге $NS = array("MODULE\_ID"=>"main").

**Примечание:** метод использует внутреннюю транзакцию. Если у вас используется **MySQL** и **InnoDB**, и ранее была открыта транзакция, то ее необходимо закрыть до подключения метода.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| MODULE\_ID | Код модуля, переиндексация которого требуется. |
| bFull | Производить ли полную переиндексацию с очисткой старых поисковых индексов. Не обязательный параметр, по умолчанию равен false. |

### Смотрите также

* [OnReIndex](/api_help/search/events/onreindex.php)

### Примеры использования

```
OnReindex.
// регистрируем обработчик события "OnReindex" модуля "search"
RegisterModuleDependences("search", "OnReindex", "my_module", "CMyModule", "OnReindex");
// создаем в модуле my_module в классе CMyModule метод OnReindex
function OnReindex()
{
	global $DB;
	$arResult = array();
	$strSql =
		"SELECT FT.ID, FT.TITLE, FT.MESSAGE, ".
		"  DATE_FORMAT(FT.POST_DATE, '%d.%m.%Y %H:%i:%s') as POST_DATE, FT.LID ".
		"FROM b_my_table FT ";
	$db_res = $DB->Query($strSql);
	while ($res = $db_res->Fetch())
	{
		$arResult[] = array(
			"ID" => $res["ID"],
			"LID" => $res["LID"],
			"DATE_CHANGE" => $res["POST_DATE"],
			"URL" => "/my_module/index.php?ID=".$res["ID"],
			"PERMISSIONS" => array(2),
			"TITLE" => $res["TITLE"],
			"BODY" => $res["POST_MESSAGE"]
		);
	}
	return $arResult;
}
// вызываем переиндексацию модуля
CSearch::ReIndexModule("my_module");
?>
Копировать
```

Новинки документации в соцсетях: