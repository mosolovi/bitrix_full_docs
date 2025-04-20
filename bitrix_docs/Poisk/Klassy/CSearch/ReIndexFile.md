[Поиск](/api_help/search/index.php)

[Классы](/api_help/search/classes/index.php)

[CSearch](/api_help/search/classes/csearch/index.php)

ReIndexFile (доступен с 3.0.1)

ReIndexFile
===========

Включить вкладки

Описание и параметры

Смотрите также

### Описание и параметры

```
int
CSearch::ReindexFile(
	string path,
	string SEARCH_SESS_ID=""
);Копировать
```

Метод переиндексирует указанный файл. Метод статический.

Сначала определяется удовлетворяет файл и его размер настройкам модуля поиска. Если одна из проверок не проходит, то возвращается 0. Затем вызываются обработчики события [OnSearchGetFileContent](/api_help/search/events/onsearchgetfilecontent.php) модуля "search". После того как один из обработчиков вернет не false, вызов остальных произведен не будет. И наконец вызывается метод [CSearch::Index](/api_help/search/classes/csearch/indexs.php)

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| path | Путь относительно корня сайта к переиндексируемому файлу. С версии **12.0.3** если **$path** не **array**, то возвращает 0. Рекомендуемый формат: `$path = array(SITE_ID, "/path/from/SiteDocRoot");` |  |
| SEARCH\_SESS\_ID | Служебный параметр, используется при пошаговой переиндексации. | 3.0.6 |

#### Возвращаемое значение

Метод возвращает уникальный идентификатор в поисковом индексе в случае успеха и 0 в противном случае.

### Смотрите также

* [OnSearchGetFileContent](/api_help/search/events/onsearchgetfilecontent.php)
* [CSearch::Index](/api_help/search/classes/csearch/indexs.php)

Новинки документации в соцсетях: