[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumMessage](/api_help/forum/developer/cforummessage/index.php)

CanUserDeleteMessage (доступен с 3.3.3)

CanUserDeleteMessage
====================

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
bool
CanUserDeleteMessage(
	int MID,
	array arUserGroups,
	int iUserID,
	bool ExternalPermission = false
);Копировать
```

Всесторонне проверяет, может ли пользователь с кодом *iUserID*, входящий в группы *arUserGroups*, удалить сообщение с кодом *ID*. Метод статический.

#### Параметры функции

| Параметр | Описание | С версии |
| --- | --- | --- |
| MID | Код сообщения, которое пользователь хочет удалить. |  |
| arUserGroups | Массив групп, в которые входит пользователь. Для текущего пользователя он возвращается методом $USER->GetUserGroupArray() |  |
| iUserID | Код пользователя. Для текущего пользователя он возвращается методом $USER->GetID() |  |
| ExternalPermission | "Приоритетное право доступа", если этот параметр передается, то не проверяются права самого форума, а идет доверие только этому параметру. Необязательный. По умолчанию равен False. | 7.1.4 |

#### Возвращаемое значение

Возвращает True, если пользователь имеет все права на удаление сообщения. В противном случае возвращается значение false.

### Смотрите также

* [CForumMessage::CanUserAddMessage](/api_help/forum/developer/cforummessage/canuseraddmessage.php)
* [CForumMessage::CanUserUpdateMessage](/api_help/forum/developer/cforummessage/canuserupdatemessage.php)

### Примеры использования

```
<?
if (CForumMessage::CanUserDeleteMessage($MID, $USER->GetUserGroupArray(), $USER->GetID()))
{
	CForumMessage::Delete($MID);
}
?>Копировать
```

Новинки документации в соцсетях: