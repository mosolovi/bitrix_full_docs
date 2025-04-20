[Конструктор отчетов](/api_help/report/index.php)

[Классы](/api_help/report/classes/index.php)

[CReport](/api_help/report/classes/creport/index.php)

sqlizeFilter (с версии 14.1.1)

sqlizeFilter
============

```
sqlizeFilter($filter);
Копировать
```

Преобразует фильтр из внутреннего формата модуля отчётов в представление, подходяещее для использования в методе *setFilter* класса *\Bitrix\Main\Entity\Query* с сохранением древовидной структуры фильтра. Используется в методе [makeSingleFilter](/api_help/report/classes/creport/makesinglefilter.php). Метод статический.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| *$filter* | Структура данных из настроек отчёта, описывающая фильтр. |

#### Возвращаемое значение

Возвращает модифицированную структуру фильтра.

Новинки документации в соцсетях: