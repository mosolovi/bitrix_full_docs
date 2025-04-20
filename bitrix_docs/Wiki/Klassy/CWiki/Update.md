[Wiki](/api_help/wiki/index.php)

[Классы](/api_help/wiki/classes/index.php)

[CWiki](/api_help/wiki/classes/cwiki/index.php)

Update (9.5.1)

Update
======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CWiki::Update(
	int ID,
	array arFields
);Копировать
```

Метод изменяет Wiki-страницу, добавляет запись в историю и обслуживает привязки к категориям. Нестатический метод.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор Wiki-страницы |
| arFields | [CIBlock::Update](/api_help/iblock/classes/ciblock/update.php) |

#### Смотрите также

* [CWiki::Add](/api_help/wiki/classes/cwiki/Add.php)
* [CWiki::UpdateCategory](/api_help/wiki/classes/cwiki/UpdateCategory.php)
* [CWiki::UpdateHistory](/api_help/wiki/classes/cwiki/UpdateHistory.php)

### Примеры использования

```
<?
// Обновим Wiki-страницу с идентификатором 13 в инфоблоке с идентификатором 2
$ID = 13;
$arFields = array(
	'IBLOCK_ID' => 2,
	'DETAIL_TEXT_TYPE' => 'html',
	'DETAIL_TEXT' => '<br/><h2>Измененная тестовая страница</h2><br/>'	
);
$CWiki = new CWiki();
if (!$CWiki->Update($ID, $arFields))
	echo 'Ошибка. Страница не изменена.';
?>Копировать
```

Новинки документации в соцсетях: