[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogPost](/api_help/blogs/classes/cblogpost/index.php)

CanUserEditPost (5.0.2)

CanUserEditPost
===============

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
bool
CBlogPost::CanUserEditPost(
	int ID,
	int userID
);Копировать
```

Метод проверяет может ли пользователь *userID* изменить сообщение *ID*. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор сообщения. |
| userID | Идентификатор пользователя. |

#### Возвращаемое значение

Метод возвращает *true* в случае если пользователь может изменить сообщение, в противном случае возвращает *false*.

### Смотрите также

* [CBlogPost](/api_help/blogs/classes/cblogpost/index.php)::[CanUserDeletePost](/api_help/blogs/classes/cblogpost/canuserdeletepost.php)

### Примеры использования

```
<?
if(CBlogPost::CanUserEditPost(1, $USER->GetID()))
	echo "Вы можете изменить сообщение.";
else
	echo "Вы не можете изменить сообщение.";
?>Копировать
```

Новинки документации в соцсетях: