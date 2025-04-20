[Wiki](/api_help/wiki/index.php)

[Классы](/api_help/wiki/classes/index.php)

[CWiki](/api_help/wiki/classes/cwiki/index.php)

Add (9.5.1)

Add
===

```
int
CWiki::Add(
	array arFields
);Копировать
```

Метод добавляет новую Wiki-страницу. Нестатический метод.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arFields | [CIBlock::Add](/api_help/iblock/classes/ciblock/add.php) |

#### Смотрите также

* [CWiki::Update](/api_help/wiki/classes/cwiki/Update.php)

#### Примеры использования

```
<?
// Добавим Wiki-страницу в инфо.блок с идентификатором 2
$arFields = array(
	'ACTIVE' => 'Y',
	'IBLOCK_ID' => 2,
	'DETAIL_TEXT_TYPE' => 'html',
	'DETAIL_TEXT' => '<br/><h2>Тестовая страница</h2><br/>',
	'NAME' => 'Тестовая страница'
);
$CWiki = new CWiki();
if (!($ID = $CWiki->Add($arFields)))
	echo 'Ошибка. Страница не создана.';
?>Копировать
```

Новинки документации в соцсетях: