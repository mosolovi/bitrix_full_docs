[Конструктор отчетов](/api_help/report/index.php)

[Классы](/api_help/report/classes/index.php)

[CReport](/api_help/report/classes/creport/index.php)

fillFilterReferenceColumns (с версии 14.1.1)

fillFilterReferenceColumns
==========================

```
fillFilterReferenceColumns(&$filters, &$fieldList, $helperClass);
Копировать
```

Проверяет, с использованием метода *fillFilterReferenceColumn* вспомогательного класса, корректность значений фильтров, ссылающихся на сущности. Алгоритм проверки и модификации фильтров определяется разработчиком метода *fillFilterReferenceColumn* вспомогательного класса отчёта. Метод статический.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| *$filters* | Ссылка на фильтры в настройках отчёта. |
| *$fieldList* | Ссылка на массив с описанием полей отчёта, который является результатом метода [getUniqueFieldsByTree](/api_help/report/classes/creport/getuniquefieldsbytree.php). |
| *$helperClass* | Имя вспомогательного класса отчёта. |

#### Возвращаемое значение

Не возвращает, модифицирует фильтры через параметр `$filters`. Модификация осуществляется методом *fillFilterReferenceColumn* вспомогательного класса отчёта, который вызывается для всех фильтров ссылочного типа.

Новинки документации в соцсетях: