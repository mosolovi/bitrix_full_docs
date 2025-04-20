[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumNew](/api_help/forum/developer/cforumnew/index.php)

CanUserDeleteForum (доступен с 3.3.3)

CanUserDeleteForum
==================

```
bool
CanUserDeleteForum(
	int FID,
	array arUserGroups,
	int iUserID,
	bool ExternalPermission = false
);Копировать
```

Всесторонне проверяет, может ли пользователь с кодом *iUserID*, входящий в группы *arUserGroups*, удалить форум с кодом *ID*. Метод статический.

#### Параметры функции

| Параметр | Описание | C версии |
| --- | --- | --- |
| FID | Код форума, который пользователь хочет удалить. |  |
| arUserGroups | Массив групп, в которые входит пользователь. Для текущего пользователя он возвращается методом $USER->GetUserGroupArray() |  |
| iUserID | Код пользователя. Для текущего пользователя он возвращается методом $USER->GetID() |  |
| ExternalPermission | "Приоритетное право доступа", если этот параметр передается, то не проверяются права самого форума, а идет доверие только этому параметру. Необязательный. По умолчанию равен False. | 7.1.4 |

#### Возвращаемое значение

Возвращает True, если пользователь имеет все права на удаление форума. В противном случае возвращается значение false.

#### Смотрите также

* [CForumNew::CanUserAddForum](/api_help/forum/developer/cforumnew/canuseraddforum.php)
* [CForumNew::CanUserUpdateForum](/api_help/forum/developer/cforumnew/canuserupdateforum.php)

Новинки документации в соцсетях: