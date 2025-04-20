[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumGroup](/api_help/forum/developer/cforumgroup/index.php)

GetLangByID (доступен с 3.3.3)

GetLangByID
===========

```
array
GetLangByID(
	int FORUM_GROUP_ID,
	char(2) strLang
);Копировать
```

Возвращает массив языковых параметров группы по ее коду *GROUP\_ID* и языку *LANG*. Метод статический.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| FORUM\_GROUP\_ID | Код группы. |
| strLang | Язык |

#### Возвращаемое значение

Массив параметров группы, зависящих от языка. Если группа не найдена, то возвращается значение false.

#### Смотрите также

* [Поля группы](/api_help/forum/fields.php#cforumgroup)

Новинки документации в соцсетях: