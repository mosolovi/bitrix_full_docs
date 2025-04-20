[Wiki](/api_help/wiki/index.php)

[Классы](/api_help/wiki/classes/index.php)

[CWiki](/api_help/wiki/classes/cwiki/index.php)

UpdateHistory (9.5.1)

UpdateHistory
=============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CWiki::UpdateHistory(
	$ID, 
	$IBLOCK_ID, 
	$modifyComment=false
);Копировать
```

Метод создает запись в истории на основе Wiki-страницы. Нестатический метод.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| ID | Идентификатор Wiki-страницы |  |
| IBLOCK\_ID | Идентификатор Инфоблока |  |
| modifyComment | Необязательный. | 12.0.1 |

#### Смотрите также

* [CWiki::Recover](/api_help/wiki/classes/cwiki/Recover.php)

### Примеры использования

```
<?
// Создадим новую запись в истории страницы с идентификатором 13 инфоблока с идентификатором 2
$ID = 13;
$IBLOCK_ID = 2;
$CWiki = new CWiki();
if (!$CWiki->UpdateHistory($ID, $IBLOCK_ID))
	echo 'Ошибка. Запись истории не создана.';
?>Копировать
```

Новинки документации в соцсетях: