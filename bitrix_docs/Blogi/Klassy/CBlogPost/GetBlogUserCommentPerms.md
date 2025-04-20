[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogPost](/api_help/blogs/classes/cblogpost/index.php)

GetBlogUserCommentPerms (5.0.2)

GetBlogUserCommentPerms
=======================

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
string
CBlogPost::GetBlogUserCommentPerms(
	int ID,
	int userID
);Копировать
```

Метод возвращает право пользователя *userID* на комментарии к сообщению *ID*. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор сообщения. |
| userID | Идентификатор пользователя. |

#### Возвращаемое значение

Метод возвращает право пользователя на комментарии к сообщению.

### Смотрите также

* [Уровни доступа к комментариям](/api_help/blogs/constant.php#)
* [CBlogPost](/api_help/blogs/classes/cblogpost/index.php)::[GetBlogUserPostPerms()](/api_help/blogs/classes/cblogpost/getbloguserpostperms.php)

### Примеры использования

```
<?
$perms = CBlogPost::GetBlogUserCommentPerms(1, $USER->GetID());
echo "Вы имеете следующее право на комментарии к сообщению: ".$perms;
?>Копировать
```

Новинки документации в соцсетях: