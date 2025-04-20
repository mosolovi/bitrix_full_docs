[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumUser](/api_help/forum/developer/cforumuser/index.php)

CanUserUpdateUser (доступно с 3.3.3 )

CanUserUpdateUser
=================

```
bool
CForumUser::CanUserUpdateUser(
	int ID,
	array arUserGroups,
	int CurrentUserID = 0
);Копировать
```

Всесторонне проверяет, может ли пользователь с кодом *iUserID*, входящий в группы *arUserGroups*, изменить профайл с кодом *ID*. Метод статический.

#### Параметры функции

| Параметр | Описание | С версии |
| --- | --- | --- |
| ID | Код профайла, который пользователь хочет изменить. |  |
| arUserGroups | Массив групп, в которые входит пользователь. Для текущего пользователя он возвращается методом `$USER->GetUserGroupArray()`. |  |
| CurrentUserID | Код пользователя. Для текущего пользователя он возвращается методом `$USER->GetID()`. |  |

#### Возвращаемое значение

Возвращает True, если пользователь имеет все права на изменение профайла. В противном случае возвращается значение false.

#### Смотрите также

* [CForumUser::CanUserAddUser](/api_help/forum/developer/cforumuser/canuseradduser.php)
* [CForumUser::CanUserDeleteUser](/api_help/forum/developer/cforumuser/canuserdeleteuser.php)

Новинки документации в соцсетях: