[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogTrackback](/api_help/blogs/classes/cblogtrackback/index.php)

SendPing (5.9.0)

SendPing
========

```
void
CBlogTrackback::SendPing(
	int   postID,
	array arPingUrls
);Копировать
```

Метод отправляет Trackback-запрос о сообщении *postID* по заданным адресам *arPingUrls*. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| postID | Идентификатор сообщения. |
| arPingUrls | Массив адресов, по которым необходимо отправить Trackback-запрос. Необязательный параметр. |

#### Примеры использования

```
<?
$ID = 2;
$arPingUrls = array(
	"/blog/trackback.php/admin-blog/1.php",
	"http://www.bitrixsoft.ru/blog/blogman/trackback.php/admin-blog/1.php"
);
CBlogTrackback::SendPing($ID, $arPingUrls);
?>Копировать
```

Новинки документации в соцсетях: