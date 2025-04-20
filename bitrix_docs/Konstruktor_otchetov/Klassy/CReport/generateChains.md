[Конструктор отчетов](/api_help/report/index.php)

[Классы](/api_help/report/classes/index.php)

[CReport](/api_help/report/classes/creport/index.php)

generateChains (с версии 14.1.1)

generateChains
==============

```
generateChains($strChains, $initEntity, $initKey);
Копировать
```

Формирует дерево объектов с полным набором всех полей, необходимых для формирования запроса выборки данных для каждого доступного поля отчёта. Метод статический.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| *$strChains* | Описание полей отчёта (возвращает метод *getColumnList* вспомогательного класса отчёта). |
| *$initEntity* | Объект базовой сущности отчёта. |
| *$initKey* | Пустая строка при обычном вызове или контекст цепочки, описывающей поле отчёта, при рекурсивном вызове. |

#### Возвращаемое значение

Возвращает массив с цепочками объектов, соответствующих описанию полей в аргументе `$strChains`. Возвращаемое значение может использоваться для построения дерева всех доступных полей отчёта методом [generateColumnTree](/api_help/report/classes/creport/generatecolumntree.php).

#### Примеры использования

```
<?
// Получение имени базовой сущности отчёта вызовом метода getEntityName вспомогательного класса.
$entityName = call_user_func(array($arParams['REPORT_HELPER_CLASS'], 'getEntityName'));
// Получение описания полей базовой сцщности отчёта вызовом метода getColumnList вспомогательного класса.
$entityFields = call_user_func(array($arParams['REPORT_HELPER_CLASS'], 'getColumnList'));
// Получение массива объектов цепочек всех доступных в отчёте полей.
$chains = CReport::generateChains($entityFields, $entity, '');
// Передача массива цепочек в метод generateColumnTree для формирования дерева с полным описанием всех
// доступных в отчёте полей.
$fieldsTree = CReport::generateColumnTree($chains, $entity, $arParams['REPORT_HELPER_CLASS']);
?>Копировать
```

Новинки документации в соцсетях: