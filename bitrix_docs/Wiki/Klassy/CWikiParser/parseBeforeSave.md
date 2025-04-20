[Wiki](/api_help/wiki/index.php)

[Классы](/api_help/wiki/classes/index.php)

[CWikiParser](/api_help/wiki/classes/cwikiparser/index.php)

parseBeforeSave (9.5.1)

parseBeforeSave
===============

```
string
CWikiParser::parseBeforeSave(
	string text,
	array &arCat
);Копировать
```

Метод обрабатывает содержимое Wiki-страницы перед сохранением. Нестатический метод.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| text | Содержимое Wiki-страницы |
| arCat | Массив будет заполнен категориями, указанными в тексте страницы |

#### Примеры использования

```
<?
$IBLOCK_ID = 2;
$NAME = 'Тестовая страница';
$arFilter = array(
	'ACTIVE' => 'Y',
	'CHECK_PERMISSIONS' => 'N',
	'IBLOCK_ID' => $IBLOCK_ID
);
$arElement = CWiki::GetElementByName($NAME, $arFilter);
$arCat = array();
$CWikiParser = new CWikiParser();
echo $CWikiParser->parseBeforeSave($arElement['~DETAIL_TEXT'], $arCat);
?>Копировать
```

Новинки документации в соцсетях: