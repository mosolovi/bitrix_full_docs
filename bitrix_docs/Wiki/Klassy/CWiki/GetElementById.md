[Wiki](/api_help/wiki/index.php)

[Классы](/api_help/wiki/classes/index.php)

[CWiki](/api_help/wiki/classes/cwiki/index.php)

GetElementById (9.5.1)

GetElementById
==============

Включить вкладки

Описание и параметры

Возвращаемое значение

Смотрите также

Примеры использования

### Описание и параметры

```
array
CWiki::GetElementById(
	int ID,
	array arFilter
);Копировать
```

Возвращает Wiki-страницу по фильтру arFilter. Статический метод.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор Wiki-страницы |
| arFilter | [GetList](/api_help/iblock/classes/ciblock/getlist.php) |

### Возвращаемое значение

Возвращается массив, содержащий поля со значениями:

| Параметр | Описание |
| --- | --- |
| NAME | наименование страницы |
| DETAIL\_TEXT\_TYPE | тип содержимого страницы |
| DETAIL\_TEXT | текст содержимого страницы |
| IMAGES | массив изображений страницы |
| SECTIONS | массив категорий страницы |
| TAGS | массив тэгов страницы |

### Смотрите также

* [CWiki::GetElementByName](/api_help/wiki/classes/cwiki/GetElementByName.php)
* [CWiki::GetCategory](/api_help/wiki/classes/cwiki/GetCategory.php)
* [CWikiParser::Parse](/api_help/wiki/classes/cwikiparser/parse.php)
* [CWikiSecurity::clear](/api_help/wiki/classes/cwikisecurity/clear.php)

### Примеры использования

```
<?
// Получим Wiki-страницу с идентификатором 13 инфоблока с идентификатором 2
$ID = 13;
$arFilter = array(
	'ACTIVE' => 'Y',
	'CHECK_PERMISSIONS' => 'N',
	'IBLOCK_ID' => 2
);
$arElement = CWiki::GetElementById($ID, $arFilter);
if ($arElement == false)
	echo 'Страница не найдена.';
?>Копировать
```

Новинки документации в соцсетях: