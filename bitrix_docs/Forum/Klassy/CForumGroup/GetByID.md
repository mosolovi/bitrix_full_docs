[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumGroup](/api_help/forum/developer/cforumgroup/index.php)

GetByID (доступен с 3.3.3)

GetByID
=======

```
array
GetByID(
	int ID
);Копировать
```

Возвращает массив не зависящих от языка параметров группы форума по ее коду *ID*. Метод статический.

#### Параметры функции

| Параметр | Описание | C версии |
| --- | --- | --- |
| ID | Код группы форума. | 3.3.3 |

#### Возвращаемое значение

Массив параметров группы, не зависящих от языка. Если группа не найдена, то возвращается значение false.

#### Смотрите также

* [Поля группы](/api_help/forum/fields.php#cforumgroup)

Новинки документации в соцсетях: