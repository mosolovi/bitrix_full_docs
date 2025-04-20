[Wiki](/api_help/wiki/index.php)

[Классы](/api_help/wiki/classes/index.php)

[CWikiSecurity](/api_help/wiki/classes/cwikisecurity/index.php)

clear (9.5.1)

clear
=====

```
string
CWikiSecurity::clear(
	string &str
);Копировать
```

Метод обрабатывает содержимое Wiki-страницы.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| str | Содержимое Wiki-страницы |

#### Смотрите также

* [CWikiParser::Parse](/api_help/wiki/classes/cwikiparser/parse.php)

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
$CWikiSecurity = new CWikiSecurity ();
$CWikiSecurity->clear($arElement['~DETAIL_TEXT']);
echo $arElement['~DETAIL_TEXT'];
?>Копировать
```

Новинки документации в соцсетях: