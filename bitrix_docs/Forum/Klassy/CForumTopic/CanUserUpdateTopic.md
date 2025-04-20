[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumTopic](/api_help/forum/developer/cforumtopic/index.php)

CanUserUpdateTopic (доступно с 3.3.3)

CanUserUpdateTopic
==================

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
bool
CForumTopic::CanUserUpdateTopic(
	int ID,
	array arUserGroups,
	int iUserID,
	bool ExternalPermission = false
);Копировать
```

Всесторонне проверяет, может ли пользователь с кодом *iUserID*, входящий в группы *arUserGroups*, изменить тему с кодом *ID*. Метод статический.

#### Параметры функции

| Параметр | Описание | C версии |
| --- | --- | --- |
| ID | Код темы, которую пользователь хочет изменить. |  |
| arUserGroups | Массив групп, в которые входит пользователь. Для текущего пользователя он возвращается методом `$USER->GetUserGroupArray()`. |  |
| iUserID | Код пользователя. Для текущего пользователя он возвращается методом `$USER->GetID()`. |  |
| ExternalPermission | "Приоритетное право доступа", если этот параметр передается, то не проверяются права самого форума, а идет доверие только этому параметру. Необязательный. По умолчанию равен False. | 7.1.4 |

#### Возвращаемое значение

Возвращает True, если пользователь имеет все права на изменение темы. В противном случае возвращается значение false.

### Смотрите также

* [CForumTopic::CanUserAddTopic](/api_help/forum/developer/cforumtopic/canuseraddtopic.php)
* [CForumTopic::CanUserDeleteTopic](/api_help/forum/developer/cforumtopic/canuserdeletetopic.php)

### Примеры использования

```
<?
if (CForumTopic::CanUserUpdateTopic($ID, $USER->GetUserGroupArray(), $USER->GetID()))
{
	echo "You can modify this topic!";
}
?>Копировать
```

Новинки документации в соцсетях: