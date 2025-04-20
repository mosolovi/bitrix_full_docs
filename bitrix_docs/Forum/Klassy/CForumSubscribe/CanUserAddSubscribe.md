[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumSubscribe](/api_help/forum/developer/cforumsubscribe/index.php)

CanUserAddSubscribe (доступен с 3.3.3)

CanUserAddSubscribe
===================

```
bool
CanUserAddSubscribe(
	int FID,
	array arUserGroups,
);Копировать
```

Всесторонне проверяет, может ли пользователь, входящий в группы *arUserGroups*, добавить новую подписку на этот форум. Метод нестатический.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| FID | ID форума, на который пользователь хочет добавить новую подписку. |
| arUserGroups | Массив групп, в которые входит пользователь. Для текущего пользователя он возвращается методом $USER->GetUserGroupArray() |

#### Возвращаемое значение

Возвращает True, если пользователь имеет право на добавление подписки. В противном случае возвращается значение False.

#### Смотрите также

* [CForumSubscribe::CanUserDeleteSubscribe](/api_help/forum/developer/cforumsubscribe/canuserdeletesubscribe.php)

Новинки документации в соцсетях: