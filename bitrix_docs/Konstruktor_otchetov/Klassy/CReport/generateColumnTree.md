[Конструктор отчетов](/api_help/report/index.php)

[Классы](/api_help/report/classes/index.php)

[CReport](/api_help/report/classes/creport/index.php)

generateColumnTree (с версии 14.1.1)

generateColumnTree
==================

```
generateColumnTree($chains, $initEntity, $helper_class, $level = 0);
Копировать
```

Формирует дерево с описанием доступных в отчёте полей с привязками к цепочкам сущностей. Метод статический.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| *$chains* | Массив с цепочками объектов, соответствующих описанию полей отчёта (результат метода [generateChains](/api_help/report/classes/creport/generatechains.php)). |
| *$initEntity* | Объект базовой сущности отчёта. |
| *$helper\_class* | Имя вспомогательного класса отчёта. |
| *$level* | Уровень рекурсии. |

#### Возвращаемое значение

Возвращает дерево с описанием доступных в отчёте полей, их метаданными, загруженными названиями и привязками к цепочкам сущностей. Например, в конструкторе отчёта, используется для построения интерфейса выбора полей в отчёт из дерева.

#### Примеры использования

```
<?
// Получение имени базовой сущности отчёта вызовом метода getEntityName вспомогательного класса.
$entityName = call_user_func(array($arParams['REPORT_HELPER_CLASS'], 'getEntityName'));
// Получение описания полей базовой сущности отчёта вызовом метода getColumnList вспомогательного класса.
$entityFields = call_user_func(array($arParams['REPORT_HELPER_CLASS'], 'getColumnList'));
// Получение массива объектов цепочек всех доступных в отчёте полей.
$chains = CReport::generateChains($entityFields, $entity, '');
// Формирование дерева с описанием доступных в отчёте полей.
$fieldsTree = CReport::generateColumnTree($chains, $entity, $arParams['REPORT_HELPER_CLASS']);
?>Копировать
```

Новинки документации в соцсетях: