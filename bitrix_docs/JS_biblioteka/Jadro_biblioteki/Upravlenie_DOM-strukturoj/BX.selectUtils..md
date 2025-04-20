[JS библиотека](/api_help/js_lib/index.php)

[Ядро библиотеки](/api_help/js_lib/kernel/index.php)

[Управление DOM-структурой](/api_help/js_lib/kernel/dom_control/index.php)

BX.selectUtils.\*

BX.selectUtils.\*
=================

Работа со списками (select).

| Метод | Описание |
| --- | --- |
| BX.selectUtils.addNewOption | Добавляет в существующий список новое значение.Добавляет в существующий список новое значение. Параметры:  | Параметр | Описание | | --- | --- | | DOMNode node | элемент DOM | | string value | значение элемента | | string name | название элемента | | boolean sort | сортировать после добавления (по умолчанию false) | | boolean unique | проверять на уникальность (по умолчанию true) | |
| BX.selectUtils.deleteOption(DOMNode node, string value) | Удаляет из указанного списка значение с указанным значением. |
| BX.selectUtils.deleteSelectedOptions(DOMNode node) | Удаляет из указанного списка все выделенные значения. |
| BX.selectUtils.deleteAllOptions(DOMNode node) | Удаляет из указанного списка все значения. |
| BX.selectUtils.sortSelect(DOMNode node) | Сортирует указанный список. |
| BX.selectUtils.selectAllOptions(DOMNode node) | Выделяет все значения указанного списка. |
| BX.selectUtils.selectOption(DOMNode node, string value) | Выделяет указанное значение указанного списка. |
| BX.selectUtils.moveOptionsUp(DOMNode node) | Перемещает выделенные значения указанного списка на одну позицию вверх. |
| BX.selectUtils.moveOptionsDown(DOMNode node) | Перемещает выделенные значения указанного списка на одну позицию вниз. |

Новинки документации в соцсетях: