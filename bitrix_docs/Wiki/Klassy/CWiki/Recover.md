[Wiki](/api_help/wiki/index.php)

[Классы](/api_help/wiki/classes/index.php)

[CWiki](/api_help/wiki/classes/cwiki/index.php)

Recover (9.5.1)

Recover
=======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CWiki::Recover(
	int HISTORY_ID,
	int ID,
	int IBLOCK_ID
);Копировать
```

Метод восстанавливает Wiki-страницу из истории. Нестатический метод.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| HISTORY\_ID | Идентификатор записи истории |
| ID | Идентификатор Wiki-страницы |
| IBLOCK\_ID | Идентификатор Инфоблока |

#### Смотрите также

* [CWiki::UpdateHistory](/api_help/wiki/classes/cwiki/UpdateHistory.php)

### Примеры использования

```
<?
// Восстановим страницу с идентификатором 13 из инфоблока с идентификатором 2 по записи в истории 26
$HISTORY_ID = 26;
$ID = 13;
$IBLOCK_ID = 2;
$CWiki = new CWiki();
if (!$CWiki->Recover($HISTORY_ID, $ID, $IBLOCK_ID))
	echo 'Ошибка. Страница не восстановлена.';
?>Копировать
```

Новинки документации в соцсетях: