[Поиск](/api_help/search/index.php)

[Классы](/api_help/search/classes/index.php)

[CSearchCustomRank](/api_help/search/classes/csearchcustomrank/index.php)

GetByID (доступен с 5.1.1)

GetByID
=======

```
CDBResult
CSearchCustomRank::GetByID(
	int ID
);Копировать
```

Получение правила сортировки по идентификатору. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор правила сортировки. |

#### Возвращаемые значения

Возвращается результат запроса типа [CDBResult](/api_help/main/reference/cdbresult/index.php).
При выборке из результата методами класса CDBResult становятся доступны поля [объекта правила сортировки](/api_help/search/classes/csearchcustomrank/fields.php).

#### Смотрите также

* [Поля объекта правила сортировки](/api_help/search/classes/csearchcustomrank/fields.php)

Новинки документации в соцсетях: