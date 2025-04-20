[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumNew](/api_help/forum/developer/cforumnew/index.php)

CanUserAddForum (доступен с 3.3.3)

CanUserAddForum
===============

```
bool
CanUserAddForum(
	array arUserGroups,
	int iUserID
);Копировать
```

Всесторонне проверяет, может ли пользователь с кодом *iUserID*, входящий в группы *arUserGroups*, добавить новый форум. Метод статический.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| arUserGroups | Массив групп, в которые входит пользователь. Для текущего пользователя он возвращается методом $USER->GetUserGroupArray() |
| iUserID | Код пользователя. Для текущего пользователя он возвращается методом $USER->GetID() |

#### Возвращаемое значение

Возвращает True, если пользователь имеет все права на добавление форума. В противном случае возвращается значение false.

#### Смотрите также

* [CForumNew::CanUserUpdateForum](/api_help/forum/developer/cforumnew/canuserupdateforum.php)
* [CForumNew::CanUserDeleteForum](/api_help/forum/developer/cforumnew/canuserdeleteforum.php)

Новинки документации в соцсетях: