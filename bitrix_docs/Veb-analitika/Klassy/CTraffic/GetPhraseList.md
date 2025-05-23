[Веб-аналитика](/api_help/statistic/index.php)

[Классы](/api_help/statistic/classes/index.php)

[CTraffic](/api_help/statistic/classes/ctraffic/index.php)

GetPhraseList

GetPhraseList
=============

Включить вкладки

Описание и параметры

Смотрите также

Структура возвращаемой записи

Примеры использования

### Описание и параметры

```
CDBResult
CTraffic::GetPhraseList(
	string &by = "s_today",
	string &order = "desc",
	array filter = array(),
	bool &is_filtered,
	mixed limit = 10,
)Копировать
```

Возвращает количество [поисковых фраз](/api_help/statistic/terms.php#search) за весь период ведения статистики, за последние 3 дня, а также за произвольный указанный интервал времени.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *by* | Поле для сортировки. Возможные значения:  * **s\_phrase** - поисковая фраза; * **s\_today** - количество поисковых фраз за сегодня; * **s\_yesterday** - количество поисковых фраз за вчера; * **s\_bef\_yesterday** - количество поисковых фраз за позавчера; * **s\_total** - суммарное количество поисковых фраз; * **s\_period** - количество поисковых фраз за установленный период времени (*filter*[**DATE1**], *filter*[**DATE2**]). |
| *оrder* | Порядок сортировки. Возможные значения:  * **asc** - по возрастанию; * **desc** - по убыванию. |
| *filter* | Массив для фильтрации результирующего списка. В массиве допустимы следующие ключи:  * **SITE\_ID** - ID сайта для которого необходимо получить статистику по поисковым фразам; * **DATE1** - начальная дата; * **DATE2** - конечная дата. |
| *is\_filtered* | Флаг отфильтрованности списка поисковых фраз. Если значение равно "true", то список был отфильтрован. |
| *limit* | Максимальное число записей результирующего списка. Если задано число >0, то число записей будет ограничено, иначе ограничений не будет. |

### Смотрите также

* [Класс "CPhrase"](/api_help/statistic/classes/cphrase/index.php)
* [Отчет "Сводная статистика"](http://www.1c-bitrix.ru/user_help/statistic/stat_list.php)

### Структура возвращаемой записи

```
Array
(
	[PHRASE] => поисковая фраза
	[TOTAL_PHRASES] => суммарное количество заходов с данной поисковой фразой
	[TODAY_PHRASES] => сколько раз сегодня заходили с данной поисковой фразой
	[YESTERDAY_PHRASES] => сколько раз вчера заходили с данной поисковой фразой
	[B_YESTERDAY_PHRASES] => сколько раз позавчера заходили с данной поисковой фразой
	[PERIOD_PHRASES] => сколько раз заходили с данной поисковой фразой за установленный период времени (filter[DATE1], filter[DATE2])
)Копировать
```

### Примеры использования

```
<?
// получим дополнительные данные за декабрь 2007 года
$arFilter = array(
	"DATE1" => "01.12.2007",
	"DATE2" => "31.12.2007"
);
// получим список поисковых фраз и статистику по ним
$rs = CTraffic::GetPhraseList(
	$by="s_today", 
	$order="desc", 
	$arFilter, 
	$is_filtered, 
	false
);
while ($ar = $rs->Fetch())
{
	echo "поисковая фраза: ".$ar["PHRASE"]."<br>";
	echo "всего заходов с данной поисковой фразой: ".
		$ar["TOTAL_PHRASES"].
		"<br>";
	echo "сегодня: ".$ar["TODAY_PHRASES"]."<br>";
	echo "вчера: ".$ar["YESTERDAY_PHRASES"]."<br>";
	echo "позавчера: ".$ar["B_YESTERDAY_PHRASES"]."<br>";
	echo "в течение декабря 2005 года: ".
		$ar["PERIOD_PHRASES"]."<br>";
}
?>Копировать
```

Новинки документации в соцсетях: