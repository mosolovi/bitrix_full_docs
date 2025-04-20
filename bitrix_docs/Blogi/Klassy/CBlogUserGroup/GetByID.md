[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogUserGroup](/api_help/blogs/classes/cblogusergroup/index.php)

GetByID (7.1.2)

GetByID
=======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
array
CBlogUserGroup::GetByID(
	int ID
);Копировать
```

Метод возвращает параметры группы пользователей блога с идентификатором *ID*. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор группы пользователей блога. |

#### Возвращаемое значение

Возвращается массив с [полями группы пользователей блога](/api_help/blogs/fields.php#usergroup).

**Примечание**

Метод использует встроенное кеширование. Таким образом, запрос к базе данных при многократном использовании метода на странице будет производиться только один раз.

### Смотрите также

* [Поля группы пользователей блога](/api_help/blogs/fields.php#usergroup)
* [CBlogUserGroup](/api_help/blogs/classes/cblogusergroup/index.php)::[GetList()](/api_help/blogs/classes/cblogusergroup/getlist.php)

### Примеры использования

```
<?
$ID = 3;
$arUserGroup = CBlogUserGroup::GetByID($ID);
if(is_array($arUserGroup))
	print_r($arUserGroup);
else
	echo "Группа пользователей не найдена.";
?>Копировать
```

Новинки документации в соцсетях: