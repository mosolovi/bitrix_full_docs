[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlog](/api_help/blogs/classes/cblog/index.php)

CanUserCreateBlog (5.0.1)

CanUserCreateBlog
=================

```
bool
CBlog::CanUserCreateBlog(
	int userID = 0
);Копировать
```

Метод проверяет, имеет ли право пользователь *userID* создать и вести блог. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| userID | Идентификатор пользователя. Необязательный. По умолчанию проверка осуществляется для текущего пользователя. |

#### Возвращаемое значение

Метод возвращает *true* в случае, если пользователь имеет право создать блог, в противном случае возвращает *false*.

#### Смотрите также

* [CBlog](/api_help/blogs/classes/cblog/index.php)::[CanUserManageBlog](/api_help/blogs/classes/cblog/canusermanageblog.php)

#### Примеры использования

```
<?
if(CBlog::CanUserCreateBlog($USER->GetID())
	echo "Вы можете создать и вести блог.";
else
	echo "Вы не можете создать и вести блог.";
?>Копировать
```

Новинки документации в соцсетях: