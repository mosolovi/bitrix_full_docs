[Веб-аналитика](/api_help/statistic/index.php)

[Классы](/api_help/statistic/classes/index.php)

[CStatEvent](/api_help/statistic/classes/cstatevent/index.php)

GetGID

GetGID
======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
string
CStatEvent::GetGID(
	mixed site_id = false
)Копировать
```

Возвращает [специальный параметр](/api_help/statistic/terms.php#gid) используемый при создании [события](/api_help/statistic/terms.php#event) в методах [CStatEvent::Add](/api_help/statistic/classes/cstatevent/add.php), [CStatEvent::AddByEvents](/api_help/statistic/classes/cstatevent/addbyevents.php).

Значение данного параметра формируется на основе нижеследующих данных текущего [посетителя](/api_help/statistic/terms.php#guest):

* краткий идентификатор портала (из настроек модуля "Статистика");
* ID [сессии](/api_help/statistic/terms.php#session);
* ID посетителя;
* двухсимвольный идентификатор страны;
* ID [рекламной кампании](/api_help/statistic/terms.php#adv);
* флаг [прямого захода](/api_help/statistic/terms.php#adv_first), либо [возврата](/api_help/statistic/terms.php#adv_back) по рекламной кампании;
* двухсимвольный идентификатор сайта.

В зависимости от значения настройки "Кодировать дополнительный параметр #EVENT\_GID# для событий" модуля "Статистика" возвращаемый параметр может быть как в открытом виде, так и в base64-кодированном виде.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *site\_id* | ID сайта. |

### Смотрите также

* [CStatEvent::DecodeGID](/api_help/statistic/classes/cstatevent/decodegid.php)
* [Термин "Специальный параметр события"](/api_help/statistic/terms.php#gid)

### Примеры использования

```
<?
// страница, на которую посетитель будет перенаправлен
// после фиксации события.
// например: платежная система или регистратор
$goto = "http://www.softkey.ru/catalog/basket.php?prodid=902&"
	"quantity=1&referer1=ritlabs_site&referer2=#EVENT_GID#";
// фиксируем событие
$goto = eregi_replace("#EVENT_GID#",
	urlencode(CStatEvent::GetGID()), 
	$goto
);
CStatEvent::AddCurrent("softkey", "out", "", "", "", $goto);
// перенаправляем посетителя
LocalRedirect($goto);
?>Копировать
```

Новинки документации в соцсетях: