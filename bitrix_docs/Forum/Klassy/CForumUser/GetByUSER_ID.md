[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumUser](/api_help/forum/developer/cforumuser/index.php)

GetByUSER\_ID (доступно с 3.3.3)

GetByUSER\_ID
=============

```
array
CForumUser::GetByUSER_ID(
	int USER_ID
);Копировать
```

Возвращает массив параметров профайла по коду *USER\_ID* пользователя, которому этот профайл принадлежит. Результаты вызова функции кешируются, поэтому повторные вызовы метода для одного и того же пользователя не требуют дополнительного обращения к базе данных (при условии, что кеш не сбросился в результате изменения параметров профайла). Метод статический.

#### Параметры функции

| Параметр | Описание | C версии |
| --- | --- | --- |
| USER\_ID | Код пользователя. |  |

#### Возвращаемое значение

Массив параметров профайла. Если профайл не найден, то возвращается значение false.

#### Смотрите также

* [Поля профайла](/api_help/forum/fields.php#cforumuser)

Новинки документации в соцсетях: