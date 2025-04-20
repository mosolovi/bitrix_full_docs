[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumSmile](/api_help/forum/developer/cforumsmile/index.php)

GetLangByID (доступен с 3.3.3)

GetLangByID
===========

```
array
GetLangByID(
	int SMILE_ID,
	char(2) strLang
);Копировать
```

Возвращает массив языковых параметров смайла по его коду *RANK\_ID* и языку *LANG*. Метод статический.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| SMILE\_ID | Код смайла. |
| strLang | Язык сайта. |

#### Возвращаемое значение

Массив языковых параметров смайла. Если смайл не найден, то возвращается значение false.

#### Смотрите также

* [Поля смайла](/api_help/forum/fields.php#cforumsmilelang)

Новинки документации в соцсетях: