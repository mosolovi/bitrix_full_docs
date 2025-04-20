[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlog](/api_help/blogs/classes/cblog/index.php)

GetByID (5.0.1)

GetByID
=======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
array
CBlog::GetByID(
	int ID
);Копировать
```

Метод возвращает параметры блога с идентификатором *ID*. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор блога. |

#### Возвращаемое значение

Возвращается массив с [полями блога](/api_help/blogs/fields.php#blog).

#### Примечание

Метод использует встроенное кеширование. Таким образом, запрос к базе данных при многократном использовании метода на странице будет производиться только один раз.

### Смотрите также

* [Поля блога](/api_help/blogs/fields.php#blog)
* [CBlog](/api_help/blogs/classes/cblog/index.php)::[GetList()](/api_help/blogs/classes/cblog/getlist.php)
* [CBlog](/api_help/blogs/classes/cblog/index.php)::[GetByOwnerID()](/api_help/blogs/classes/cblog/getbyownerid.php)

### Примеры использования

```
<?
$ID = 1;
$arBlog = CBlog::GetByID($ID);
if(is_array($arBlog))
	print_r($arBlog);
else
	echo "Блог не найден";
?>Копировать
```

Новинки документации в соцсетях: