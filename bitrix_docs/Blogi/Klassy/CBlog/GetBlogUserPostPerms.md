[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlog](/api_help/blogs/classes/cblog/index.php)

GetBlogUserPostPerms (5.0.1)

GetBlogUserPostPerms
====================

```
string
CBlog::GetBlogUserPostPerms(
	int ID,
	int userID
);Копировать
```

Метод возвращает право пользователя *userID* на сообщения блога *ID*. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор блога. |
| userID | Идентификатор пользователя. |

#### Возвращаемое значение

Метод возвращает право пользователя на сообщения блога.

#### Смотрите также

* [Уровни доступа к сообщениям блога](/api_help/blogs/constant.php#pperms)
* [CBlog](/api_help/blogs/classes/cblog/index.php)::[GetBlogUserCommentPerms()](/api_help/blogs/classes/cblog/getblogusercommentperms.php)

#### Примеры использования

```
<?
$perms = CBlog::GetBlogUserPostPerms(1, $USER->GetID());
echo "Вы имеете следующее право на сообщения блога: ".$perms;
?>Копировать
```

Новинки документации в соцсетях: