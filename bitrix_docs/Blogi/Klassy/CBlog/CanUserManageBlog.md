[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlog](/api_help/blogs/classes/cblog/index.php)

CanUserManageBlog (5.0.1)

CanUserManageBlog
=================

```
bool
CBlog::CanUserManageBlog(
	int ID,
	int userID
);Копировать
```

Метод проверяет, может ли пользователь *userID* управлять блогом *ID*. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор блога. |
| userID | Идентификатор пользователя. Необязательный параметр. |

#### Возвращаемое значение

Метод возвращает *true* в случае, если пользователь может управлять блогом, в противном случае возвращает *false*.

#### Смотрите также

* [CBlog](/api_help/blogs/classes/cblog/index.php)::[CanUserCreateBlog](/api_help/blogs/classes/cblog/canusercreateblog.php)

#### Примеры использования

```
<?
if(CBlog::CanUserManageBlog(1, $USER->GetID())
	echo "Вы можете управлять блогом.";
else
	echo "Вы не можете управлять блогом.";
?>Копировать
```

Новинки документации в соцсетях: