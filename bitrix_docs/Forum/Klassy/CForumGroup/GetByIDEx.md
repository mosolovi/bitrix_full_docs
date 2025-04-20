[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumGroup](/api_help/forum/developer/cforumgroup/index.php)

GetByIDEx

GetByIDEx
=========

```
array
GetByIDEx(
	int ID,
	char(2) LANGUAGE_ID
);Копировать
```

Возвращает массив всех параметров группы по ее коду *ID* и языку *LANGUAGE\_ID*. Метод статический.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| ID | Код группы. |
| LANGUAGE\_ID | Язык.     До версии 8.0.0 параметр назывался strLang. |

#### Возвращаемое значение

Массив всех параметров группы, включая зависящие от языка. Если группа не найдена, то возвращается значение false.

#### Смотрите также

* [Поля группы](/api_help/forum/fields.php#cforumgroup)

Новинки документации в соцсетях: