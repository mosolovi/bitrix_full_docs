[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumMessage](/api_help/forum/developer/cforummessage/index.php)

CanUserUpdateMessage (доступен с 3.3.3)

CanUserUpdateMessage
====================

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
bool
CanUserUpdateMessage(
	int MID,
	array arUserGroups,
	int iUserID,
	bool ExternalPermission = false
);Копировать
```

Всесторонне проверяет, может ли пользователь с кодом *iUserID*, входящий в группы *arUserGroups*, изменить сообщение с кодом *ID*. Метод статический.

#### Параметры функции

| Параметр | Описание | C версии |
| --- | --- | --- |
| MID | Код сообщения, которое пользователь хочет изменить. |  |
| arUserGroups | Массив групп, в которые входит пользователь. Для текущего пользователя он возвращается методом $USER->GetUserGroupArray() |  |
| iUserID | Код пользователя. Для текущего пользователя он возвращается методом $USER->GetID() |  |
| ExternalPermission | "Приоритетное право доступа", если этот параметр передается, то не проверяются права самого форума, а идет доверие только этому параметру. Необязательный. По умолчанию равен False. | 7.1.4 |

#### Возвращаемое значение

Возвращает True, если пользователь имеет все права на изменение сообщения. В противном случае возвращается значение false.

### Смотрите также

* [CForumMessage::CanUserAddMessage](/api_help/forum/developer/cforummessage/canuseraddmessage.php)
* [CForumMessage::CanUserDeleteMessage](/api_help/forum/developer/cforummessage/canuserdeletemessage.php)

### Примеры использования

```
<?
if (CForumMessage::CanUserUpdateMessage($MID, $USER->GetUserGroupArray(), $USER->GetID()))
{
	echo "You can modify this message!";
}
?>Копировать
```

Новинки документации в соцсетях: