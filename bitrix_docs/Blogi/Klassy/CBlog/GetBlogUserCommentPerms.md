[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlog](/api_help/blogs/classes/cblog/index.php)

GetBlogUserCommentPerms (5.0.1)

GetBlogUserCommentPerms
=======================

```
string
CBlog::GetBlogUserCommentPerms(
	int ID,
	int userID
);Копировать
```

Метод возвращает право пользователя *userID* на комментарии блога *ID*. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор блога. |
| userID | Идентификатор пользователя. |

#### Возвращаемое значение

Метод возвращает право пользователя на комментарии блога.

#### Смотрите также

* [Уровни доступа к комментариям](/api_help/blogs/constant.php#)
* [CBlog](/api_help/blogs/classes/cblog/index.php)::[GetBlogUserPostPerms()](/api_help/blogs/classes/cblog/getbloguserpostperms.php)

#### Примеры использования

```
<?
$perms = CBlog::GetBlogUserCommentPerms(1, $USER->GetID());
echo "Вы имеете следующее право на комментарии блога: ".$perms;
?>Копировать
```

Новинки документации в соцсетях: