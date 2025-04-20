[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumUser](/api_help/forum/developer/cforumuser/index.php)

Delete (доступно с 3.3.3)

Delete
======

```
bool
CForumUser::Delete(
	int ID
);Копировать
```

Удаляет профайл с кодом *ID*. Метод статический.

#### Параметры функции

| Параметр | Описание | C версии |
| --- | --- | --- |
| ID | Код профайла, которую необходимо удалить. |  |

#### Возвращаемое значение

Возвращает True в случае успешного удаления, в противном случае возвращает False.

#### Смотрите также

* Перед удалением профайла следует проверить возможность удаления методом [CForumUser::CanUserDeleteUser](/api_help/forum/developer/cforumuser/canuserdeleteuser.php)

Новинки документации в соцсетях: