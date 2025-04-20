[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogComment](/api_help/blogs/classes/cblogcomment/index.php)

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
CBlogComment::GetByID(
	int ID
);Копировать
```

Метод возвращает параметры комментария с идентификатором *ID*. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор комментария. |

#### Возвращаемое значение

Возвращается массив с [полями комментария](/api_help/blogs/fields.php#comment).

#### Примечание

Метод использует встроенное кэширование. Таким образом, запрос к базе данных при многократном использовании метода на странице будет производиться только один раз.

### Смотрите также

* [CBlogComment](/api_help/blogs/classes/cblogcomment/index.php)::[GetList()](/api_help/blogs/classes/cblogcomment/getlist.php)
* [Поля комментария к сообщению](/api_help/blogs/fields.php#comment)

### Примеры использования

```
<?
$ID = 1;
$arComment = CBlogComment::GetByID($ID);
if(is_array($arComment))
	print_r($arComment);
else
	echo "Комментарий не найден.";
?>Копировать
```

Новинки документации в соцсетях: