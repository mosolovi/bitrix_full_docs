[Поиск](/api_help/search/index.php)

[Классы](/api_help/search/classes/index.php)

[CSearchCustomRank](/api_help/search/classes/csearchcustomrank/index.php)

Add (доступен с 5.1.1)

Add
===

```
int
CSearchCustomRank::Add(
	array arFields
);Копировать
```

Метод добавляет новое правило. Нестатический метод.

После удаления всех требуемых правил необходимо пересчитать поисковый индекс методами [CSearchCustomRank::StartUpdates](/api_help/search/classes/csearchcustomrank/startupdate.php) и [CSearchCustomRank::NextUpdate](/api_help/search/classes/csearchcustomrank/nextupdate.php).

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arFields | Массив со значениями полей [объекта правила сортировки](/api_help/search/classes/csearchcustomrank/fields.php). |

#### Возвращаемые значения

В случае успешного добавления возвращается ID нового правила. В противном случае возвращается false.

#### Смотрите также

* [Поля объекта правила сортировки](/api_help/search/classes/csearchcustomrank/fields.php)
* [CSearchCustomRank::StartUpdates](/api_help/search/classes/csearchcustomrank/startupdate.php)
* [CSearchCustomRank::NextUpdate](/api_help/search/classes/csearchcustomrank/nextupdate.php)

Новинки документации в соцсетях: