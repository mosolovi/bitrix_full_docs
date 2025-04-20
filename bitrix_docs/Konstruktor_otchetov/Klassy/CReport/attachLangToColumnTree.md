[Конструктор отчетов](/api_help/report/index.php)

[Классы](/api_help/report/classes/index.php)

[CReport](/api_help/report/classes/creport/index.php)

attachLangToColumnTree (с версии 14.1.1)

attachLangToColumnTree
======================

```
attachLangToColumnTree(&$tree, $initEntity, $helper_class, $preTitle = array());
Копировать
```

Загружает языковые фразы для полей отчёта, используя описания сущностей и вспомогательный класс отчёта. Метод статический.

**Примечание**. Используется внутри метода generateColumnTree.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| *$tree* | Ссылка на дерево с описанием доступных в отчёте полей, формируемое методом [generateColumnTree](/api_help/report/classes/creport/generatecolumntree.php), в котором необходимо загрузить языковые фразы. |
| *$initEntity* | Объект базовой сущности отчёта. |
| *$helper\_class* | Имя вспомогательного класса отчёта. |
| *$preTitle* | Префикс для полного названия поля. |

#### Возвращаемое значение

Не возвращает, модифицирует параметр `$tree`.

Новинки документации в соцсетях: