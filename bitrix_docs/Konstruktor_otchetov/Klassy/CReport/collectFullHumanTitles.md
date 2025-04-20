[Конструктор отчетов](/api_help/report/index.php)

[Классы](/api_help/report/classes/index.php)

[CReport](/api_help/report/classes/creport/index.php)

collectFullHumanTitles (с версии 14.1.1)

collectFullHumanTitles
======================

```
collectFullHumanTitles($tree);
Копировать
```

Формирует массив названий для всех доступных полей отчёта на основе информации, возвращаемой методом [generateColumnTree](/api_help/report/classes/creport/generatecolumntree.php). Метод статический.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| *$tree* | Дерево с описанием доступных в отчёте полей, результат вызова метода [generateColumnTree](/api_help/report/classes/creport/generatecolumntree.php). |

#### Возвращаемое значение

Массив, ключами которого являются определения полей отчёта, а значениями - их полные названия.

Новинки документации в соцсетях: