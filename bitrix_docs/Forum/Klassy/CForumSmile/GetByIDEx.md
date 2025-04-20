[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumSmile](/api_help/forum/developer/cforumsmile/index.php)

GetByIDEx (доступен с 3.3.3)

GetByIDEx
=========

```
array
GetByIDEx(
	int ID,
	char(2) strLang
);Копировать
```

Возвращает массив всех параметров смайла по его коду *ID* и языку *LANG*. Метод статический.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| ID | Код смайла. |
| strLang | Язык сайта. |

#### Возвращаемое значение

Массив всех параметров смайла. Если смайл не найден, то возвращается значение false.

#### Смотрите также

* [Поля смайла](/api_help/forum/fields.php#cforumsmile)

Новинки документации в соцсетях: