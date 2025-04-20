[Веб-аналитика](/api_help/statistic/index.php)

[Классы](/api_help/statistic/classes/index.php)

[CStatEvent](/api_help/statistic/classes/cstatevent/index.php)

DecodeGID

DecodeGID
=========

Включить вкладки

Описание и параметры

Возвращаемое значение

Смотрите также

Примеры использования

### Описание и параметры

```
array
CStatEvent::DecodeGID(
	string gid
)Копировать
```

Декодирует [специальный параметр](/api_help/statistic/terms.php#gid) используемый при создании [события](/api_help/statistic/terms.php#event) в методах [CStatEvent::Add](/api_help/statistic/classes/cstatevent/add.php), [CStatEvent::AddByEvents](/api_help/statistic/classes/cstatevent/addbyevents.php). Метод успешно декодирует параметр как в открытом виде, так и в base64-кодированном.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *gid* | Специальный параметр события. |

### Возвращаемое значение

Метод возвращает массив вида:

  

```
Array
(
	[SESSION_ID] => ID сессии
	[GUEST_ID] => ID посетителя
	[COUNTRY_ID] => ID страны
	[ADV_ID] => ID рекламной кампании
	[ADV_BACK] => Y - возврат по рекламной кампании; N - прямой заход
	[SITE_ID] => ID сайта
)Копировать
```

### Смотрите также

* [CStatEvent::GetGID](/api_help/statistic/classes/cstatevent/getgid.php)
* [Термин "Специальный параметр события"](/api_help/statistic/terms.php#gid)

### Примеры использования

```
<?
// раскодируем специальный параметр события
$arr = CStatEvent::DecodeGID("BITRIX_SM.OTk1LjgyLk4wLjI1Lk4ucnU%3D");
// распечатаем результирующий массив
echo "<pre>"; print_r($arr); echo "</pre>";
?>Копировать
```

Новинки документации в соцсетях: