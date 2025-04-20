[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockRSS](/api_help/iblock/classes/ciblockrss/index.php)

XMLDate2Dec (доступен с 3.0.16)

XMLDate2Dec
===========

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
string
CIBlockRSS::XMLDate2Dec(
	string dateXML,
	string dateFormat= "DD.MM.YYYY"
);Копировать
```

Преобразует дату из rss формата в формат "DD.MM.YYYY". Нестатический метод.

**Примечание**: под rss форматом даты понимается формат, описанный в rfc 822.

#### Параметры вызова

| Параметр | Описание | С версии |
| --- | --- | --- |
| dateXML | rss дата/время. |  |
| dateFormat | Формат даты. Необязательный параметр. По умолчанию используется формат "DD.MM.YYYY". | 11.0.7 |

#### Возвращаемое значение

строка.

### Смотрите также

* <http://www.w3.org/Protocols/rfc822/>
* [CIBlockRSS](/api_help/iblock/classes/ciblockrss/index.php)::[GetNewsEx](/api_help/iblock/classes/ciblockrss/getnewsex.php)
* [CIBlockRSS](/api_help/iblock/classes/ciblockrss/index.php)::[FormatArray](/api_help/iblock/classes/ciblockrss/formatarray.php)

### Примеры использования

```
<?
$arXML = CIBlockRSS::GetNewsEx('www.1c-bitrix.ru', '80', '/bitrix/rss.php', 'ID=news_sm&LANG=ru&TYPE=news&LIMIT=5');
if(count($arXML) > 0)
{
	$arRSS = CIBlockRSS::FormatArray($arXML);
	foreach($arRSS["item"] as $arItem)
	{
		echo $arItem["title"].":".CIBlockRSS::XMLDate2Dec($arItem["pubDate"]);
	}
}
?>Копировать
```

Новинки документации в соцсетях: