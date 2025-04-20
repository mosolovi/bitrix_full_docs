[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumSmile](/api_help/forum/developer/cforumsmile/index.php)

GetByID (доступен с 3.3.3)

GetByID
=======

```
array
GetByID(
	int ID
);Копировать
```

Возвращает массив параметров смайла, которые не зависят от языка, по его коду *ID*. Метод статический.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| ID | Код смайла. |

#### Возвращаемое значение

Массив параметров смайла. Если смайл не найден, то возвращается значение false.

#### Смотрите также

* [Поля смайла](/api_help/forum/fields.php#cforumsmile)

Новинки документации в соцсетях: