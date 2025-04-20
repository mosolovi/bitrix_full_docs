[Wiki](/api_help/wiki/index.php)

[Классы](/api_help/wiki/classes/index.php)

[CWikiUtils](/api_help/wiki/classes/cwikiutils/index.php)

getRightsLink (9.5.1)

getRightsLink
=============

```
array
CWikiUtils::getRightsLink(
	array arPage
);Копировать
```

Возвращает массив ссылок для меню. Статический метод.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arPage | Массив условий формирования |

#### Возвращаемое значение

Возвращается массив ссылок, содержащих поля со значениями:

| Параметр | Описание |
| --- | --- |
| NAME | наименование ссылки |
| TITLE | наименование ссылки для подсказки |
| LINK | ссылка на страницу |
| CURRENT | является ли эта ссылка текущей |
| ID | идентификатор ссылки |
| IS\_RED | является ли ссылка красной |

#### Примеры использования

```
<?
// выведем меню страницы редактирования Wiki-страницы
$arPage = array('article', 'edit');
$arMenu = CWikiUtils::getRightsLinks($arPage);
?>
<?
// выведем меню страницы история
$arPage = array('article', 'history');
$arMenu = CWikiUtils::getRightsLinks($arPage);
?>
<?
// выведем меню страницы просмотра версии страницы
$arPage = array('article', 'history_diff');
$arMenu = CWikiUtils::getRightsLinks($arPage);
?>Копировать
```

Новинки документации в соцсетях: