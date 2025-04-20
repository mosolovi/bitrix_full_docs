[Конструктор отчетов](/api_help/report/index.php)

[Классы](/api_help/report/classes/index.php)

[CReport](/api_help/report/classes/creport/index.php)

isValidFilterCompareVariation (с версии 14.1.1)

isValidFilterCompareVariation
=============================

```
isValidFilterCompareVariation($fDefinition, $fType, $variation, $variations);
Копировать
```

Проверяет применимость операции сравнения к полю отчёта в фильтре. Метод статический.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| *$fDefinition* | Определение поля в фильтре отчёта. |
| *$fType* | Тип поля в фильтре отчёта. |
| *$variation* | Операция сравнения, заданная для фильтра. |
| *$variations* | Информация о допустимых операциях сравнения для полей отчёта. Обычно возвращается методом *getCompareVariations* вспомогательного класса отчёта. |

#### Возвращаемое значение

Возвращает `true`, если операция сравнения применима к полю фильтра, иначе `false`.

Новинки документации в соцсетях: