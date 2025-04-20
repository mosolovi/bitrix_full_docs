[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumUser](/api_help/forum/developer/cforumuser/index.php)

CanUserAddUser (доступно с 3.3.3)

CanUserAddUser
==============

```
bool
CForumUser::CanUserAddUser(
	array arUserGroups
);Копировать
```

Всесторонне проверяет, может ли пользователь, входящий в группы *arUserGroups*, добавить новый профайл. Метод статический.

#### Параметры функции

| Параметр | Описание | С версии |
| --- | --- | --- |
| arUserGroups | Массив групп, в которые входит пользователь. Для текущего пользователя он возвращается методом `$USER->GetUserGroupArray()`. |  |

#### Возвращаемое значение

Возвращает True, если пользователь имеет все права на добавление профайла. В противном случае возвращается значение false.

#### Смотрите также

* [CForumUser::CanUserUpdateUser](/api_help/forum/developer/cforumuser/canuserupdateuser.php)
* [CForumUser::CanUserDeleteUser](/api_help/forum/developer/cforumuser/canuserdeleteuser.php)

Новинки документации в соцсетях: