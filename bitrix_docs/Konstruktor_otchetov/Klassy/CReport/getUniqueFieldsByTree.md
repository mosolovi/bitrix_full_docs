[Конструктор отчетов](/api_help/report/index.php)

[Классы](/api_help/report/classes/index.php)

[CReport](/api_help/report/classes/creport/index.php)

getUniqueFieldsByTree (с версии 14.1.1)

getUniqueFieldsByTree
=====================

```
getUniqueFieldsByTree($tree);
Копировать
```

Формирует полный список доступных в отчёте полей из основной и связанных сущностей на основе информации, возвращаемой методом [generateColumnTree](/api_help/report/classes/creport/generatecolumntree.php). Другими словами, разворачивает информацию о полях из древовидной структуры, возвращённой методом [generateColumnTree](/api_help/report/classes/creport/generatecolumntree.php), в список, ключами которого являются определения полей отчёта относительно базовой сущности. Метод статический.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| *$tree* | Дерево с описанием доступных в отчёте полей, результат вызова метода [generateColumnTree](/api_help/report/classes/creport/generatecolumntree.php). |

#### Возвращаемое значение

Массив, ключами которого являются определения полей относительно базовой сущности, а значениями - объекты, описывающие поля отчёта.

**Примечание**. Результат используется для быстрого получения объектов, описывающих поля, по их определению.

Новинки документации в соцсетях: