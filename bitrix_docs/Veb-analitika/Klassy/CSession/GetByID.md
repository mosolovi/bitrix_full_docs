[Веб-аналитика](/api_help/statistic/index.php)

[Классы](/api_help/statistic/classes/index.php)

[CSession](/api_help/statistic/classes/csession/index.php)

GetByID

GetByID
=======

Включить вкладки

Описание и параметры

Структура возвращаемой записи

Примеры использования

### Описание и параметры

```
CDBResult
CSession::GetByID(
	int session_id
)Копировать
```

Возвращает данные по указанной [сессии](/api_help/statistic/terms.php#session).

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *session\_id* | ID сессии. |

#### Смотрите также

* [Термин "Сессия"](/api_help/statistic/terms.php#session)

### Структура возвращаемой записи

```
Array
(
	[ID] => ID сессии
	[GUEST_ID] => ID посетителя
	[NEW_GUEST] => [Y|N] флаг "новый посетитель"
	[USER_ID] => ID пользователя, под которым последний раз был авторизован посетитель
	[USER_AUTH] => [Y|N] флаг "был ли посетитель авторизован в данной сессии"
	[LOGIN] => логин пользователя, под которым последний раз был авторизован посетитель
	[USER_NAME] => имя и фамилия пользователя, под которым последний раз был авторизован посетитель
	[C_EVENTS] => количество событий, произведенных в данной сесси
	[HITS] => количество хитов данной сессии
	[FAVORITES] => [Y|N] флаг "добавлял ли посетитель сайт в "Избранное" в данной сессии"
	[URL_FROM] => ссылающаяся страница для первого хита сессии
	[URL_TO] => первая страница сессии
	[URL_TO_404] => [Y|N] флаг 404 ошибки на первой странице сессии
	[URL_LAST] => последняя страница сессии
	[URL_LAST_404] => [Y|N] флаг 404 ошибки на первой странице сессии
	[USER_AGENT] => UserAgent посетителя
	[DATE_STAT] => дата начала сессии
	[DATE_FIRST] => время первого хита сессии
	[DATE_LAST] => время последнего хита сессии
	[SESSION_TIME] => разница во времени между первым и последним хитом сессии (сек.)
	[IP_FIRST] => IP адрес посетителя на первом хите сессии (в виде: XXX.XXX.XXX.XXX)
	[IP_FIRST_NUMBER] => IP адрес посетителя на первом хите сессии (в числовом представлении)
	[IP_LAST] => IP адрес посетителя на последнем хите сессии (в виде: XXX.XXX.XXX.XXX)
	[IP_LAST_NUMBER] => IP адрес посетителя на последнем хите сессии (в числовом представлении)
	[FIRST_HIT_ID] => ID первого хита
	[FIRST_SITE_ID] => ID сайта для первого хита сессии
	[LAST_HIT_ID] => ID последнего хита
	[LAST_SITE_ID] => ID сайта для последнего хита сессии
	[ADV_ID] => ID рекламной кампании
	[ADV_BACK] => [Y|N] флаг прямого захода (N) или возврата (Y) по рекламной кампании
	[REFERER1] => идентификатор referer1 рекламной кампании
	[REFERER2] => идентификатор referer2 рекламной кампании
	[REFERER3] => дополнительный параметр referer3 рекламной кампании
	[COUNTRY_ID] => ID страны посетителя
	[COUNTRY_NAME] => название страны посетителя
	[STOP_LIST_ID] => ID записи стоп-листа, под которую попал посетитель (если это имело место быть)
	[PHPSESSID] => идентификатор сессии выданный PHP
)Копировать
```

### Примеры использования

```
<?
$session_id = 1;
if ($rs = CSession::GetByID($session_id))
{
	$ar = $rs->Fetch();
	// выведем параметры сессии
	echo "<pre>"; print_r($ar); echo "</pre>";
}
?>Копировать
```

Новинки документации в соцсетях: