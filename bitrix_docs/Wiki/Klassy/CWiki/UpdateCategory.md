[Wiki](/api_help/wiki/index.php)

[Классы](/api_help/wiki/classes/index.php)

[CWiki](/api_help/wiki/classes/cwiki/index.php)

UpdateCategory (9.5.1)

UpdateCategory
==============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
void
CWiki::UpdateCategory(
	int ID,
	int IBLOCK_ID,
	array arCats
);Копировать
```

Метод обновляет привязки Wiki-страницы к категориям. Нестатический метод.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор Wiki-страницы |
| IBLOCK\_ID | Идентификатор Инфоблока |
| arCats | Массив наименований категорий страницы |

#### Смотрите также

* [CWiki::GetCategory](/api_help/wiki/classes/cwiki/GetCategory.php)

### Примеры использования

```
<?
// Обновим категории страницы с идентификатором 13 из инфоблока с идентификатором 2
$arCats = array('Категория 1', 'Категория 2');
$ID = 13;
$IBLOCK_ID = 2;
$CWiki = new CWiki();
$CWiki->UpdateCategory($ID, $IBLOCK_ID, $arCats);
?>Копировать
```

Новинки документации в соцсетях: