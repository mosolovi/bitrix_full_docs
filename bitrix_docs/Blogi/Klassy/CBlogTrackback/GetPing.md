[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogTrackback](/api_help/blogs/classes/cblogtrackback/index.php)

GetPing (5.9.0)

GetPing
=======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
void
CBlogTrackback::GetPing(
	string blogUrl,
	int    postID,
	array  arParams
);Копировать
```

Метод принимает и сохраняет Trackback-запрос *arParams* к сообщению *postID* блога с адресом *blogUrl*. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| blogUrl | Адрес блога. |
| postID | Идентификатор сообщения. |
| arParams | Массив параметров Trackback-запроса:  * **title**  - обязательный, заголовок Trackback'а; * **url**  - обязательный, адрес Trackback'a; * **excerpt**  - текст Trackback'а; * **blog\_name**  - название блога.  Необязательный параметр. |

### Примеры использования

```
<?
if (CModule::IncludeModule("blog"))
{
	$postID = IntVal($postID);
	$blogUrl = Trim($blogUrl);
	if (strtoupper($_SERVER["REQUEST_METHOD"]) != "POST")
	{
		LocalRedirect(CBlogPost::PreparePath($blogUrl, $postID));
		die();
	}
	$arParams = array();
	if (isset($_REQUEST))
	{
		if (isset($_REQUEST["title"]))
			$arParams["title"] = $_REQUEST["title"];
		if (isset($_REQUEST["url"]))
			$arParams["url"] = $_REQUEST["url"];
		if (isset($_REQUEST["excerpt"]))
			$arParams["excerpt"] = $_REQUEST["excerpt"];
		if (isset($_REQUEST["blog_name"]))
			$arParams["blog_name"] = $_REQUEST["blog_name"];
	}
	CBlogTrackback::GetPing($blogUrl, $postID, $arParams);
}
?>Копировать
```

Новинки документации в соцсетях: