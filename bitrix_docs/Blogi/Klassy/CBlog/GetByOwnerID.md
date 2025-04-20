[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlog](/api_help/blogs/classes/cblog/index.php)

GetByOwnerID (5.0.1)

GetByOwnerID
============

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
array
CBlog::GetByOwnerID(
	int userID,
	$arGroup = Array()
);Копировать
```

Метод возвращает блог пользователя с идентификатором *userID*. Метод нестатический.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| userID | Идентификатор пользователя. |  |
| arGroup | ИД групп блогов (массив целых чисел). Необязательный параметр. | 8.0.5 |

#### Возвращаемое значение

Возвращается массив с [полями блога](/api_help/blogs/fields.php#blog).

#### Примечание

Метод использует встроенное кеширование. Таким образом, запрос к базе данных при многократном использовании метода на странице будет производиться только один раз.

### Смотрите также

* [Поля блога](/api_help/blogs/fields.php#blog)
* [CBlog](/api_help/blogs/classes/cblog/index.php)::[GetList()](/api_help/blogs/classes/cblog/getlist.php)

### Примеры использования

```
<?
$arBlog = CBlog::GetByOwnerID($ID);
if(is_array($arBlog))
	print_r($arBlog);
else
	echo "Блог не найден";
?>Копировать
```

Новинки документации в соцсетях: