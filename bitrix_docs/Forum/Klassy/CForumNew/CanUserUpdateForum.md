[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumNew](/api_help/forum/developer/cforumnew/index.php)

CanUserUpdateForum (доступен с 3.3.3)

CanUserUpdateForum
==================

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
bool
CanUserUpdateForum(
	int FID,
	array arUserGroups,
	int iUserID,
	bool ExternalPermission = false
);Копировать
```

Всесторонне проверяет, может ли пользователь с кодом *iUserID*, входящий в группы *arUserGroups*, изменить форум с кодом *ID*. Метод статический.

#### Параметры функции

| Параметр | Описание | C версии |
| --- | --- | --- |
| FID | Код форума, который пользователь хочет изменить. |  |
| arUserGroups | Массив групп, в которые входит пользователь. Для текущего пользователя он возвращается методом $USER->GetUserGroupArray() |  |
| iUserID | Код пользователя. Для текущего пользователя он возвращается методом $USER->GetID() |  |
| ExternalPermission | "Приоритетное право доступа", если этот параметр передается, то не проверяются права самого форума, а идет доверие только этому параметру. Необязательный. По умолчанию равен False. | 7.1.4 |

#### Возвращаемое значение

Возвращает True, если пользователь имеет все права на изменение форума. В противном случае возвращается значение false.

### Смотрите также

* [CForumNew::CanUserAddForum](/api_help/forum/developer/cforumnew/canuseraddforum.php)
* [CForumNew::CanUserDeleteForum](/api_help/forum/developer/cforumnew/canuserdeleteforum.php)

### Примеры использования

```
<?
if (CForumNew::CanUserUpdateForum($FID, $USER->GetUserGroupArray(), $USER->GetID()))
{
	echo "You can modify this forum!";
}
?>Копировать
```

Новинки документации в соцсетях: