[Wiki](/api_help/wiki/index.php)

[Классы](/api_help/wiki/classes/index.php)

[CWiki](/api_help/wiki/classes/cwiki/index.php)

GetElementByName (9.5.1)

GetElementByName
================

Включить вкладки

Описание и параметры

Возвращаемое значение

Смотрите также

Примеры использования

### Описание и параметры

```
result_type
CWiki::GetElementByName(
	string NAME,
	array arFilter,
	arComponentParams = array()
);Копировать
```

Возвращает Wiki-страницу по фильтру arFilter. Статический метод.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| NAME | Название Wiki-страницы |  |
| arFilter | [GetList](/api_help/iblock/classes/ciblock/getlist.php) |  |
| arComponentParams | Необязательный. | 12.0.1 |

### Возвращаемое значение

Возвращается массив, содержащий поля со значениями:

| Параметр | Описание |
| --- | --- |
| NAME | наименование страницы |
| DETAIL\_TEXT\_TYPE | тип содержимого страницы |
| DETAIL\_TEXT | текст содержимого страницыы |
| IMAGES | массив изображений страницы |
| SECTIONS | массив категорий страницы |
| TAGS | массив тэгов страницы |

### Смотрите также

* [CWiki::GetElementById](/api_help/wiki/classes/cwiki/GetElementById.php)
* [CWiki::GetCategory](/api_help/wiki/classes/cwiki/GetCategory.php)
* [CWikiParser::Parse](/api_help/wiki/classes/cwikiparser/parse.php)
* [CWikiSecurity::clear](/api_help/wiki/classes/cwikisecurity/clear.php)

### Примеры использования

```
<?
// Получим Wiki-страницу с названием "Тестовая страница" инфоблока с идентификатором 2
$NAME = 'Тестовая страница';
$arFilter = array(
	'ACTIVE' => 'Y',
	'CHECK_PERMISSIONS' => 'N',
	'IBLOCK_ID' => 2
);
$arElement = CWiki::GetElementByName($NAME, $arFilter);
if ($arElement == false)
	echo 'Страница не найдена.';
?>Копировать
```

Новинки документации в соцсетях: