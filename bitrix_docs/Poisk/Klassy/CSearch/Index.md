[Поиск](/api_help/search/index.php)

[Классы](/api_help/search/classes/index.php)

[CSearch](/api_help/search/classes/csearch/index.php)

Index (доступен с 3.0.1)

Index
=====

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
int
CSearch::Index(
	string MODULE_ID,
	string ITEM_ID,
	array arFields,
	bool bOverWrite = false,
	string SEARCH_SESS_ID = ''
);Копировать
```

Метод переиндексирует какую-то одиночную позицию (сообщение на форуме, новость и т.п.), причем комбинация (MODULE\_ID, ITEM\_ID) используется для определения переиндексируемого документа. Метод статический.

Вначале индексации вызывается событие [BeforeIndex](/api_help/search/events/beforeindex.php). Затем вычисляется пользовательский вес позиции. И производится собственно переиндексация.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| MODULE\_ID | Код модуля, которому принадлежит индексируемый элемент. |  |
| ITEM\_ID | Код индексируемого элемента. |  |
| arFields | Массив свойств индексируемого элемента. |  |
| bOverWrite | Перетирать индекс поиска элемента если элемент уже проиндексирован. Не обязательный параметр, по умолчанию равен false. |  |
| SEARCH\_SESS\_ID | Служебный параметр, используется при пошаговой переиндексации. | 3.0.6 |

### Примеры использования

```
<?
CSearch::Index(
	"iblock",
	$ID,
	Array(
		"DATE_CHANGE"=>$arIBlockElement["DATE_CHANGE"],
		"TITLE"=>$arIBlockElement["NAME"],
		"SITE_ID"=>$arSites,
		"PARAM1"=>$arIBlockElement["IBLOCK_TYPE_ID"],
		"PARAM2"=>$IBLOCK_ID,
		"PERMISSIONS"=>$arGroups,
		"URL"=>str_replace("#ID#", $arIBlockElement["ID"], $DETAIL_PAGE_URL),
		"BODY"=>$arIBlockElement["DETAIL_TEXT"],
		"TAGS"=>$arIBlockElement["TAGS"]
	),
	$bOverWrite
);
?>
Копировать
```

Новинки документации в соцсетях: