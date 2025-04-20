[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogUser](/api_help/blogs/classes/cbloguser/index.php)

GetByID (5.0.2)

GetByID
=======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
array
CBlogUser::GetByID(
	int ID,
	int selectType = BLOG_BY_BLOG_USER_ID
);Копировать
```

Метод возвращает параметры пользователя блога с идентификатором *ID*. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор пользователя. |
| selectType | Тип выборки. Может принимать следующие значения:  * **BLOG\_BY\_BLOG\_USER\_ID** - найти пользователя по идентификатору пользователя блога; * **BLOG\_BY\_USER\_ID** - найти пользователя по идентификатору пользователя сайта.  Необязательный. По умолчанию равен *BLOG\_BY\_BLOG\_USER\_ID*. |

#### Возвращаемое значение

Возвращается массив с [полями пользователя блога](/api_help/blogs/fields.php#user).

**Примечание**

Метод использует встроенное кеширование. Таким образом, запрос к базе данных при многократном использовании метода на странице будет производиться только один раз.

### Смотрите также

* [CBlogUser](/api_help/blogs/classes/cbloguser/index.php)::[GetList()](/api_help/blogs/classes/cbloguser/getlist.php)
* [Поля пользователя блога](/api_help/blogs/fields.php#user)

### Примеры использования

```
<?
$ID = $USER->GetID();
$arUser = CBlogUser::GetByID($ID, BLOG_BY_USER_ID);
if(is_array($arUser))
	print_r($arUser);
else
	echo "Пользователь не найден.";
?>Копировать
```

Новинки документации в соцсетях: