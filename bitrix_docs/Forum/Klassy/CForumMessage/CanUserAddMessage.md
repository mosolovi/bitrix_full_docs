[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumMessage](/api_help/forum/developer/cforummessage/index.php)

CanUserAddMessage (доступен с 3.3.3)

CanUserAddMessage
=================

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
bool
CanUserAddMessage(
	int TID,
	array arUserGroups,
	int iUserID,
	bool ExternalPermission = false
);Копировать
```

Всесторонне проверяет, может ли пользователь с кодом *iUserID*, входящий в группы *arUserGroups*, добавить новое сообщение в тему *TID*. Метод статический.

#### Параметры функции

| Параметр | Описание | C версии |
| --- | --- | --- |
| TID | Код темы, в которую пользователь хочет добавить сообщение. |  |
| arUserGroups | Массив групп, в которые входит пользователь. Для текущего пользователя он возвращается методом $USER->GetUserGroupArray() |  |
| iUserID | Код пользователя. Для текущего пользователя он возвращается методом $USER->GetID() |  |
| ExternalPermission | "Приоритетное право доступа", если этот параметр передается, то не проверяются права самого форума, а идет доверие только этому параметру. Необязательный. По умолчанию равен False. | 7.1.4 |

#### Возвращаемое значение

Возвращает True, если пользователь имеет все права на добавление сообщения. В противном случае возвращается значение false.

### Смотрите также

* [CForumMessage::CanUserUpdateMessage](/api_help/forum/developer/cforummessage/canuserupdatemessage.php)
* [CForumMessage::CanUserDeleteMessage](/api_help/forum/developer/cforummessage/canuserdeletemessage.php)

### Примеры использования

```
<?
if (CForumMessage::CanUserAddMessage($TID, $USER->GetUserGroupArray(), $USER->GetID()))
{
	echo "You can add message!";
}
?>Копировать
```

Новинки документации в соцсетях: