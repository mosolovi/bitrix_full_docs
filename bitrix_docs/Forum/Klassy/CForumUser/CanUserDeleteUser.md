[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumUser](/api_help/forum/developer/cforumuser/index.php)

CanUserDeleteUser (доступно с 3.3.3)

CanUserDeleteUser
=================

```
bool
CForumUser::CanUserDeleteUser(
	int ID,
	array arUserGroups
);Копировать
```

Всесторонне проверяет, может ли пользователь, входящий в группы *arUserGroups*, удалить профайл с кодом *ID*. Метод статический.

#### Параметры функции

| Параметр | Описание | С версии |
| --- | --- | --- |
| ID | Код профайла, который пользователь хочет удалить. |  |
| arUserGroups | Массив групп, в которые входит пользователь. Для текущего пользователя он возвращается методом $USER->GetUserGroupArray() |  |

#### Возвращаемое значение

Возвращает True, если пользователь имеет все права на удаление профайла. В противном случае возвращается значение false.

#### Смотрите также

* [CForumUser::CanUserAddUser](/api_help/forum/developer/cforumuser/canuseradduser.php)
* [CForumUser::CanUserUpdateUser](/api_help/forum/developer/cforumuser/canuserupdateuser.php)

Новинки документации в соцсетях: