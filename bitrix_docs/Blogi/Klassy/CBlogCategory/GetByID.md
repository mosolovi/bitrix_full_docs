[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogCategory](/api_help/blogs/classes/cblogcategory/index.php)

GetByID (6.5.1)

GetByID
=======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
array
CBlogCategory::GetByID(
	int ID
);Копировать
```

Метод возвращает параметры категории с идентификатором *ID*. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор категории. |

#### Возвращаемое значение

Возвращается массив вида:

```
Array(
	"ID" => "ID категории",
	"BLOG_ID" => "ID блога",
	"NAME" => "Название категории"
)Копировать
```

Если категория не найдена метод вернет *false*.

#### Примечание

Метод использует встроенное кеширование. Таким образом, запрос к базе данных при многократном использовании метода на странице будет производиться только один раз.

### Смотрите также

* [CBlogCategory](/api_help/blogs/classes/cblogcategory/index.php)::[GetList()](/api_help/blogs/classes/cblogcategory/getlist.php)

### Примеры использования

```
<?
$ID = 1;
$arCategory = CBlogCategory::GetByID($ID);
if(is_array($arCategory))
	print_r($arCategory);
else
	echo "Категория не найдена.";
?>Копировать
```

Новинки документации в соцсетях: