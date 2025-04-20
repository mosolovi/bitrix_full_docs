[Поиск](/api_help/search/index.php)

[Классы](/api_help/search/classes/index.php)

[CSearchCustomRank](/api_help/search/classes/csearchcustomrank/index.php)

Delete (доступен с 5.1.1)

Delete
======

```
CDBResult
CSearchCustomRank::Delete(
	int ID
);Копировать
```

Удаление правила сортировки по идентификатору. Метод статический.

После удаления всех требуемых правил необходимо пересчитать поисковый индекс методами [CSearchCustomRank::StartUpdates](/api_help/search/classes/csearchcustomrank/startupdate.php) и
[CSearchCustomRank::NextUpdate](/api_help/search/classes/csearchcustomrank/nextupdate.php).

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор правила сортировки. |

#### Возвращаемые значения

Если правило успешно удалено, то возвращается результат запроса типа [CDBResult](/api_help/main/reference/cdbresult/index.php), в противном случае метод вернет false.

#### Смотрите также

* [CSearchCustomRank::StartUpdates](/api_help/search/classes/csearchcustomrank/startupdate.php)
* [CSearchCustomRank::NextUpdate](/api_help/search/classes/csearchcustomrank/nextupdate.php)

Новинки документации в соцсетях: