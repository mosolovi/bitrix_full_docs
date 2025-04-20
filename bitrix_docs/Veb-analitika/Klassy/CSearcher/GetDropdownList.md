[Веб-аналитика](/api_help/statistic/index.php)

[Классы](/api_help/statistic/classes/index.php)

[CSearcher](/api_help/statistic/classes/csearcher/index.php)

GetDropdownList

GetDropdownList
===============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
CDBResult
CSearcher::GetDropdownList(
	string order = "ORDER BY NAME, ID"
)Копировать
```

Возвращает список [поисковых систем](/api_help/statistic/terms.php#search) для вывода его в выпадающем списке с помощью функции [SelectBox](/api_help/main/functions/html/selectbox.php), либо в списке множественного выбора с помощью функции [SelectBoxM](/api_help/main/functions/html/selectboxm.php).

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *order* | SQL код, позволяющий задать произвольную сортировку результирующего списка. |

#### Смотрите также

* [CSearcher::GetList](/api_help/statistic/classes/csearcher/getlist.php)
* [Термин "Поисковая система"](/api_help/statistic/terms.php#search)

### Примеры использования

```
<?
// выпадающий список с одиночным выбором
echo SelectBox(
	"SEARCHER_ID", 
	CSearcher::GetDropdownList(), 
	"", 
	intval($SEARCHER_ID)
);
// список из 20 видимых элементов с возможностью множественного выбора
echo SelectBoxM(
	"arSEARCHER_ID[]", 
	CSearcher::GetDropdownList(), 
	$arSEARCHER_ID, 
	"", 
	false, 
	20
);
?>Копировать
```

Новинки документации в соцсетях: