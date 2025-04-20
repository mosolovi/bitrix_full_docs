[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogSitePath](/api_help/blogs/classes/cblogsitepath/index.php)

GetBySiteID (5.9.1)

GetBySiteID
===========

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
array
CBlogSitePath::GetBySiteID(
	string siteID
);Копировать
```

Метод возвращает параметры пути сайта *siteID*. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| siteID | Идентификатор сайта. |

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
* [CBlogSitePath](/api_help/blogs/classes/cblogsitepath/index.php)::[GetByID()](/api_help/blogs/classes/cblogsitepath/getbyid.php)

### Примеры использования

```
<?
$SiteID = "ru";
$arSitePath = CBlogSitePath::GetBySiteID($SiteID);
if(is_array($arSitePath))
	print_r($arSitePath);
else
	echo "Путь не найден.";
?>Копировать
```

Новинки документации в соцсетях: