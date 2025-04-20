[Поиск](/api_help/search/index.php)

[События](/api_help/search/events/index.php)

OnReIndex (доступен с 3.0.4)

OnReIndex
=========

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
bool
функция-обработчик(
	array NS,
	string oCallback,
	string callback_method
);Копировать
```

Событие "OnReindex" вызывается во время переиндексации данных модуля методами [CSearch::ReindexModule](/api_help/search/classes/csearch/reindexmodule.php) или [CSearch::ReIndexAll](/api_help/search/classes/csearch/reindexall.php).

#### Параметры

| Параметр | Описание |
| --- | --- |
| NS | Массив в котором передается информация о начале текущего шага.  * **MODULE** - идентификатор модуля; * **ID** - идентификатор элемента; * **SITE\_ID** - массив сайтов; |
| oCallback | Объект модуля поиска для вызова метода индексации элемента. |
| callback\_method | Метод объекта модуля поиска для индексации элемента. |

### Смотрите также

* [CSearch::ReindexModule](/api_help/search/classes/csearch/reindexmodule.php)
* [CSearch::ReIndexAll](/api_help/search/classes/csearch/reindexall.php)
* [Обработка событий](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Примеры использования

```
<?
// регистрируем обработчик события "OnReindex" модуля "search"
RegisterModuleDependences("search", "OnReindex", "my_module", "CMyModule", "OnReindex");
// создаем в модуле my_module в классе CMyModule функцию-метод OnReindex
public static function OnReindex($NS, $oCallback, $callback_method)
{
	global $DB;
	$NS["ID"] = intval($NS["ID"]);
	if($NS["MODULE"]=="my_module" && $NS["ID"] > 0)
		$strWhere = "WHERE ID > ".$NS["ID"];
	else
		$strWhere = "";
	$strSql =
		"SELECT FT.ID, FT.TITLE, FT.MESSAGE, ".
		"  DATE_FORMAT(FT.POST_DATE, '%d.%m.%Y %H:%i:%s') as POST_DATE, FT.LID ".
		"FROM b_my_table FT ".
		$strWhere.
		" ORDER BY FT.ID";
	$db_res = $DB->Query($strSql);
	while ($res = $db_res->Fetch())
	{
		$Result = array(
			"ID" => $res["ID"],
			"SITE_ID" => array("s1"),
			"DATE_CHANGE" => $res["POST_DATE"],
			"URL" => "/my_module/index.php?ID=".$res["ID"],
			"PERMISSIONS" => array(2),
			"TITLE" => $res["TITLE"],
			"BODY" => $res["MESSAGE"],
		);
		$index_res = call_user_func(array($oCallback, $callback_method), $Result);
		if(!$index_res)
			return $Result["ID"];
	}
	return false;
}
// вызываем переиндексацию модуля
CSearch::ReIndexModule("my_module");
?>Копировать
```

Новинки документации в соцсетях: