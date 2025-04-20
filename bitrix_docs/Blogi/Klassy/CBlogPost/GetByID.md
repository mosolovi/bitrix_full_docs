[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogPost](/api_help/blogs/classes/cblogpost/index.php)

GetByID (5.0.6)

GetByID
=======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
array
CBlogPost::GetByID(
	int ID
);Копировать
```

Метод возвращает параметры сообщения с идентификатором *ID*. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор сообщения. |

#### Возвращаемое значение

Возвращается массив с [полями сообщения](/api_help/blogs/fields.php#post).

#### Примечание

Метод использует встроенное кэширование. Таким образом, запрос к базе данных при многократном использовании метода на странице будет производиться только один раз.

### Смотрите также

* [Поля блога](/api_help/blogs/fields.php#blog)
* [CBlogPost](/api_help/blogs/classes/cblogpost/index.php)::[GetList()](/api_help/blogs/classes/cblogpost/getlist.php)

### Примеры использования

```
<?
$ID = 1;
$arPost = CBlogPost::GetByID($ID);
if(is_array($arPost))
	print_r($arPost);
else
	echo "Сообщение не найдено";
?>Копировать
```

Новинки документации в соцсетях: