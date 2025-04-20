[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumTopic](/api_help/forum/developer/cforumtopic/index.php)

CanUserAddTopic (доступно с 3.3.3)

CanUserAddTopic
===============

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
bool
CForumTopic::CanUserAddTopic(
	int FID,
	array arUserGroups,
	int iUserID = 0,
	bool arForum = false,
	bool ExternalPermission = false
);Копировать
```

Всесторонне проверяет, может ли пользователь с кодом *iUserID*, входящий в группы *arUserGroups*, добавить новую тему в форум *FID*. Метод статический.

#### Параметры функции

| Параметр | Описание | C версии |
| --- | --- | --- |
| FID | Код форума, в который пользователь хочет добавить тему. |  |
| arUserGroups | Массив групп, в которые входит пользователь. Для текущего пользователя он возвращается методом `$USER->GetUserGroupArray()`. |  |
| iUserID | Код пользователя. Для текущего пользователя он возвращается методом `$USER->GetID()`. |  |
| arForum | Необязательный. По умолчанию равен False. | 4.0.3 |
| ExternalPermission | "Приоритетное право доступа", если этот параметр передается, то не проверяются права самого форума, а идет доверие только этому параметру. Необязательный. По умолчанию равен False. | 7.1.4 |

#### Возвращаемое значение

Возвращает True, если пользователь имеет все права на добавление темы. В противном случае возвращается значение false.

### Смотрите также

* [CForumTopic::CanUserUpdateTopic](/api_help/forum/developer/cforumtopic/canuserupdatetopic.php)
* [CForumTopic::CanUserDeleteTopic](/api_help/forum/developer/cforumtopic/canuserdeletetopic.php)

### Примеры использования

```
<?
if (CForumTopic::CanUserAddTopic(
	$FID, 
	$USER->GetUserGroupArray(), 
	$USER->GetID()
))
{
	echo "You can add topic!";
}
?>Копировать
```

Новинки документации в соцсетях: