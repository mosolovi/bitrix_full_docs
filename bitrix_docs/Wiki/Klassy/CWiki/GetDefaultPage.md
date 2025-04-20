[Wiki](/api_help/wiki/index.php)

[Классы](/api_help/wiki/classes/index.php)

[CWiki](/api_help/wiki/classes/cwiki/index.php)

GetDefaultPage (9.5.1)

GetDefaultPage
==============

```
string
CWiki::GetDefaultPage(
	int IBLOCK_ID
);Копировать
```

Метод возвращает Wiki-страницу по-умолчанию. Нестатический метод.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| IBLOCK\_ID | Идентификатор Инфоблока.   До версии 10.0.0 назвался **BLOCK\_ID**. |

#### Смотрите также

* [CWiki::SetDefaultPage](/api_help/wiki/classes/cwiki/SetDefaultPage.php)

#### Примеры использования

```
<?
// Получим страницу по умолчанию инфоблока с идентификатором 2
$IBLOCK_ID = 2;
$NAME = CWiki::GetDefaultPage($IBLOCK_ID);
if (strlen($NAME) <= 0)
	echo 'Ошибка. Страница по умолчанию не установлена.';
?>Копировать
```

Новинки документации в соцсетях: