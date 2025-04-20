[Wiki](/api_help/wiki/index.php)

[Классы](/api_help/wiki/classes/index.php)

[CWiki](/api_help/wiki/classes/cwiki/index.php)

Rename (9.5.1)

Rename
======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CWiki::Rename(
	int ID,
	array arFields,
	bUpdateSearch=true
);Копировать
```

Метод изменяет Wiki-страницу, добавляет запись в историю и обслуживает привязки к категориям. Нестатический метод.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| ID | Идентификатор Wiki-страницы |  |
| arFields | [CIBlock::Update](/api_help/iblock/classes/ciblock/update.php) |  |
| UpdateSearch | Необязательный. | 12.0.1 |

#### Смотрите также

* [CWiki::Update](/api_help/wiki/classes/cwiki/Update.php)

### Примеры использования

```
<?
// Переименуем Wiki-страницу с идентификатором 13 в инфоблоке с идентификатором 2
$ID = 13;
$arFields = array(
	'IBLOCK_ID' => 2,
	'NAME' => 'Измененная тестовая страница'	
);
$CWiki = new CWiki();
if (!$CWiki->Rename($ID, $arFields))
	echo 'Ошибка. Страница не переименована.';
?>Копировать
```

Новинки документации в соцсетях: