[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogPost](/api_help/blogs/classes/cblogpost/index.php)

CanUserDeletePost (5.0.2)

CanUserDeletePost
=================

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
bool
CBlogPost::CanUserDeletePost(
	int ID,
	int userID
);Копировать
```

Метод проверяет может ли пользователь *userID* удалить сообщение *ID*. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор сообщения. |
| userID | Идентификатор пользователя. |

#### Возвращаемое значение

Метод возвращает *true* в случае если пользователь может удалить сообщение, в противном случае возвращает *false*.

### Смотрите также

* [CBlogPost](/api_help/blogs/classes/cblogpost/index.php)::[CanUserEditPost](/api_help/blogs/classes/cblogpost/canusereditpost.php)

### Примеры использования

```
<?
if(CBlogPost::CanUserDeletePost(1, $USER->GetID()))
	echo "Вы можете удалить сообщение.";
else
	echo "Вы не можете удалить сообщение.";
?>Копировать
```

Новинки документации в соцсетях: