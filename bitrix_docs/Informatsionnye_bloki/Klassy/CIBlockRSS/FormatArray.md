[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockRSS](/api_help/iblock/classes/ciblockrss/index.php)

FormatArray (доступен с 3.0.15)

FormatArray
===========

Включить вкладки

Описание и параметры

Возвращаемое значение

Смотрите также

Примеры использования

### Описание и параметры

```
array
CIBlockRSS::FormatArray(
	array arRes,
	array bOutChannel = false
);Копировать
```

Метод преобразует результат метода [CIBlockRSS](/api_help/iblock/classes/ciblockrss/index.php)::[GetNewsEx](/api_help/iblock/classes/ciblockrss/getnewsex.php) в более приемлемое представление. Нестатический метод.

#### Параметры вызова

| Параметр | Описание | С версии |
| --- | --- | --- |
| arRes | Массив описания xml. Результат работы метода [CIBlockRSS](/api_help/iblock/classes/ciblockrss/index.php)::[GetNewsEx.](/api_help/iblock/classes/ciblockrss/getnewsex.php) |  |
| *bOutChannel* | Параметр должен быть синхронизирован с одноименным метода [CIBlockRSS](/api_help/iblock/classes/ciblockrss/index.php)::[GetNewsEx](/api_help/iblock/classes/ciblockrss/getnewsex.php). | 3.2.1 |

### Возвращаемое значение

Массив следующего вида:

* title - заголовок rss ленты;
* link - ссылка;
* description - описание;
* lastBuildDate - время в rss формате (см. [CIBlockRSS](/api_help/iblock/classes/ciblockrss/index.php)::[XMLDate2Dec](/api_help/iblock/classes/ciblockrss/xmldate2dec.php));
* ttl - время действия в минутах;
* image - описание картинки:

+ title - заголовок;
+ url;
+ link - ссылка;
+ width - ширина;
+ height - высота;

* item - массив элементами которого являются нововсти:

+ title - заголовок новости;
+ link - ссылка;
+ description - подробное описание;
+ enclosure - вложение (не обязательно):

- url;
- length;
- type;
- width - не обязательно;
- height - не обязательно;

+ category - категория;
+ pubDate - время в rss формате (см. [CIBlockRSS](/api_help/iblock/classes/ciblockrss/index.php)::[XMLDate2Dec](/api_help/iblock/classes/ciblockrss/xmldate2dec.php));

### Смотрите также

* [CIBlockRSS](/api_help/iblock/classes/ciblockrss/index.php)::[GetNewsEx](/api_help/iblock/classes/ciblockrss/getnewsex.php)
* [CIBlockRSS](/api_help/iblock/classes/ciblockrss/index.php)::[XMLDate2Dec](/api_help/iblock/classes/ciblockrss/xmldate2dec.php)

### Примеры использования

```
<?
$arXML = CIBlockRSS::GetNewsEx('www.1c-bitrix.ru', '80', '/bitrix/rss.php', 'ID=news_sm&LANG=ru&TYPE=news&LIMIT=5');
if(count($arXML) > 0)
{
	$arRSS = CIBlockRSS::FormatArray($arXML);
	print_r($arRSS);
}
?>Копировать
```

Новинки документации в соцсетях: