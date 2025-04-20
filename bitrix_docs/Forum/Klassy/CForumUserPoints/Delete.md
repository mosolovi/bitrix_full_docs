[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumUserPoints](/api_help/forum/developer/cforumuserpoints/index.php)

Delete (доступно с 3.3.7)

Delete
======

```
bool
CForumUserPoints::Delete(
	int FROM_USER_ID, 
	int TO_USER_ID
);Копировать
```

Функция удаляет из голосования голоса, отданные пользователем с кодом FROM\_USER\_ID пользователю с кодом TO\_USER\_ID. Метод нестатический.

#### Параметры функции

| Параметр | Описание | С версии |
| --- | --- | --- |
| FROM\_USER\_ID | Код пользователя, отдавшего голос. |  |
| TO\_USER\_ID | Код пользователя, которому был отдан голос. |  |

#### Возвращаемые значения

Функция возвращает True в случае успешного удаления и False - в случае ошибки.

Новинки документации в соцсетях: