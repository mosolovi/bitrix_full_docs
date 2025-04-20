[Wiki](/api_help/wiki/index.php)

[Классы](/api_help/wiki/classes/index.php)

[CWiki](/api_help/wiki/classes/cwiki/index.php)

SetDefaultPage (9.5.1)

SetDefaultPage
==============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CWiki::SetDefaultPage(
	int IBLOCK_ID,
	string NAME
);Копировать
```

Метод устанавливает Wiki-страницу по-умолчанию. Нестатический метод.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| IBLOCK\_ID | Идентификатор Инфоблока.  До версии 10.0.0 назывался **BLOCK\_ID**. |
| NAME | Наименование страницы |

#### Смотрите также

* [CWiki::GetDefaultPage](/api_help/wiki/classes/cwiki/GetDefaultPage.php)

### Примеры использования

```
<?
// Установим страницу "Тестовая страница" страницей по умолчанию инфоблока с идентификатором 2
$IBLOCK_ID = 2;
$NAME = 'Тестовая страница';
if (!CWiki::SetDefaultPage($IBLOCK_ID, $NAME))
	echo 'Ошибка. Страница по умолчанию не установлена.';
?>Копировать
```

Новинки документации в соцсетях: