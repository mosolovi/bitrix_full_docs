[Wiki](/api_help/wiki/index.php)

[Классы](/api_help/wiki/classes/index.php)

[CWiki](/api_help/wiki/classes/cwiki/index.php)

Delete (9.5.1)

Delete
======

```
bool
CWiki::Delete(
	int ID,
	int IBLOCK_ID,
);Копировать
```

Метод удаляет Wiki-страницу. Нестатический метод.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор Wiki-страницы |
| IBLOCK\_ID | Идентификатор Инфоблока.   До версии 10.0.0 назывался **BLOCK\_ID**. |

#### Примеры использования

```
<?
// Удалим Wiki-страницу с идентификатором 13 в инфоблоке с идентификатором 2
$ID = 13;
$IBLOCK_ID = 2;
$CWiki = new CWiki();
if (!$CWiki->Delete($ID, $IBLOCK_ID))
	echo 'Ошибка. Страница не удалена.';
?>Копировать
```

Новинки документации в соцсетях: