[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumTopic](/api_help/forum/developer/cforumtopic/index.php)

CanUserDeleteTopic (доступно с 3.3.3)

CanUserDeleteTopic
==================

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
bool
CForumTopic::CanUserDeleteTopic(
	int ID,
	array arUserGroups,
	int iUserID,
	bool ExternalPermission = false
);Копировать
```

Всесторонне проверяет, может ли пользователь с кодом *iUserID*, входящий в группы *arUserGroups*, удалить тему с кодом *ID*. Метод статический.

#### Параметры функции

| Параметр | Описание | C версии |
| --- | --- | --- |
| ID | Код темы, которую пользователь хочет удалить. |  |
| arUserGroups | Массив групп, в которые входит пользователь. Для текущего пользователя он возвращается методом $USER->GetUserGroupArray() |  |
| iUserID | Код пользователя. Для текущего пользователя он возвращается методом $USER->GetID() |  |
| ExternalPermission | "Приоритетное право доступа", если этот параметр передается, то не проверяются права самого форума, а идет доверие только этому параметру. Необязательный. По умолчанию равен False. | 7.1.4 |

#### Возвращаемое значение

Возвращает True, если пользователь имеет все права на удаление темы. В противном случае возвращается значение false.

### Смотрите также

* [CForumTopic::CanUserAddTopic](/api_help/forum/developer/cforumtopic/canuseraddtopic.php)
* [CForumTopic::CanUserUpdateTopic](/api_help/forum/developer/cforumtopic/canuserupdatetopic.php)

### Примеры использования

```
<?
if (CForumTopic::CanUserDeleteTopic($ID, $USER->GetUserGroupArray(), $USER->GetID()))
{
	CForumTopic::Delete($ID);
}
?>Копировать
```

Новинки документации в соцсетях: