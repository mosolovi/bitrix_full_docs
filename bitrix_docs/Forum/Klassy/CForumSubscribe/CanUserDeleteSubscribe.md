[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumSubscribe](/api_help/forum/developer/cforumsubscribe/index.php)

CanUserDeleteSubscribe (доступно с 3.3.3)

CanUserDeleteSubscribe
======================

```
bool
CanUserDeleteSubscribe(
	int ID,
	array arUserGroups,
	int CurrentUserID = 0
);Копировать
```

Всесторонне проверяет, может ли пользователь с кодом *CurrentUserID*, входящий в группы *arUserGroups*, удалить подписку с кодом *ID*. Метод статический.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| ID | Код подписки, которую пользователь хочет удалить. |
| arUserGroups | Массив групп, в которые входит пользователь. Для текущего пользователя он возвращается методом $USER->GetUserGroupArray() |
| CurrentUserID | Код пользователя. Для текущего пользователя он возвращается методом $USER->GetID() |

#### Возвращаемое значение

Возвращает True, если пользователь имеет все права на удаление подписки. В противном случае возвращается значение false.

#### Смотрите также

* [CForumSubscribe::CanUserAddSubscribe](/api_help/forum/developer/cforumsubscribe/canuseraddsubscribe.php)

Новинки документации в соцсетях: