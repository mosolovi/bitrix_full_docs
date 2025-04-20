[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogSitePath](/api_help/blogs/classes/cblogsitepath/index.php)

GetByID (5.9.1)

GetByID
=======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
array
CBlogSitePath::GetByID(
	int ID
);Копировать
```

Метод возвращает параметры пути с идентификатором *ID*. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор пути. |

#### Возвращаемое значение

Возвращается массив вида:

```
Array(
	"ID" => "ID пути",
	"SITE_ID" => "ID сайта",
	"PATH" => "Путь"
)Копировать
```

Если путь не найден метод вернет *false*.

**Примечание**

Метод использует встроенное кеширование. Таким образом, запрос к базе данных при многократном использовании метода на странице будет производиться только один раз.

### Смотрите также

* [CBlogSitePath](/api_help/blogs/classes/cblogsitepath/index.php)::[GetList()](/api_help/blogs/classes/cblogsitepath/getlist.php)
* [CBlogSitePath](/api_help/blogs/classes/cblogsitepath/index.php)::[GetBySiteID()](/api_help/blogs/classes/cblogsitepath/getbysiteid.php)

### Примеры использования

```
<?
$ID = 1;
$arSitePath = CBlogSitePath::GetByID($ID);
if(is_array($arSitePath))
	print_r($arSitePath);
else
	echo "Путь не найден.";
?>Копировать
```

Новинки документации в соцсетях: