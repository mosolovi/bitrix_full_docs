[Wiki](/api_help/wiki/index.php)

[Классы](/api_help/wiki/classes/index.php)

[CWikiParser](/api_help/wiki/classes/cwikiparser/index.php)

Parse (9.5.1)

Parse
=====

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
string
CWikiParser::Parse(
	string text,
	type = 'text',
	arFile = array(),
	arParams = array()
);Копировать
```

Метод обрабатывает содержимое Wiki-страницы. Нестатический метод.

#### Параметры метода

| Параметр | Описание | С версии | До версии |
| --- | --- | --- | --- |
| text | Содержимое Wiki-страницы |  |  |
| type | Тип содержимого Wiki-страницы (html|text). Необязательный. |  |  |
| arFile | Массив изображений. Необязательный. | 9.5.4 |  |
| siteDir | Путь до папки. Необязательный. | 11.5.1 | 12.0.1 |
| arParams | Массив параметров. Необязательный. | 12.0.1 |  |

#### Возвращаемое значение

Возвращает обработанную Wiki-страницу, без Wiki-разметки.

### Смотрите также

* [CWikiSecurity::clear](/api_help/wiki/classes/cwikisecurity/clear.php)

### Примеры использования

```
<?
// Обработаем содержимое страницы "Тестовая страница" инфоблока с идентификатором 2
$IBLOCK_ID = 2;
$NAME = 'Тестовая страница';
$arFilter = array(
	'ACTIVE' => 'Y',
	'CHECK_PERMISSIONS' => 'N',
	'IBLOCK_ID' => $IBLOCK_ID
);
$arElement = CWiki::GetElementByName($NAME, $arFilter);
$CWikiParser = new CWikiParser();
echo $CWikiParser->Parse($arElement['~DETAIL_TEXT'], $arElement['DETAIL_TEXT_TYPE'], $arElement['IMAGES']);
?>Копировать
```

Новинки документации в соцсетях: