[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogPost](/api_help/blogs/classes/cblogpost/index.php)

GetBlogUserPostPerms (5.0.2)

GetBlogUserPostPerms
====================

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
string
CBlogPost::GetBlogUserPostPerms(
	int ID,
	int userID
);Копировать
```

Метод возвращает право пользователя *userID* на сообщение *ID*. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор сообщения. |
| userID | Идентификатор пользователя. |

#### Возвращаемое значение

Метод возвращает право пользователя на сообщение.

### Смотрите также

* [Уровни доступа к сообщениям](/api_help/blogs/constant.php#pperms)
* [CBlogPost](/api_help/blogs/classes/cblogpost/index.php)::[GetBlogUserCommentPerms()](/api_help/blogs/classes/cblogpost/getblogusercommentperms.php)

### Примеры использования

```
<?
$perms = CBlogPost::GetBlogUserPostPerms(1, $USER->GetID());
echo "Вы имеете следующее право на сообщение: ".$perms;
?>Копировать
```

Новинки документации в соцсетях: