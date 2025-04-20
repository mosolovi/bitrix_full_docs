[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskCheckListItem](/api_help/tasks/classes/ctaskchecklistitem/index.php)

isActionAllowed (17.6.11)

isActionAllowed
===============

```
\CTaskCheckListItem::isActionAllowed($actionId)Копировать
```

Метод проверяет доступ к действиям над пунктами чеклиста.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| *$actionId* | Идентификатор действия:  * \CTaskCheckListItem::**ACTION\_ADD** = 0x01; // добавление * \CTaskCheckListItem::**ACTION\_MODIFY** = 0x02; // изменение * \CTaskCheckListItem::**ACTION\_REMOVE** = 0x03; // удаление * \CTaskCheckListItem::**ACTION\_TOGGLE** = 0x04; // выполнение * \CTaskCheckListItem::**ACTION\_REORDER** = 0x05; // сортировка |

#### Примеры использования

```
$task = \CTaskItem::getInstance($taskId, $userId);
echo $task->isActionAllowed(\CTaskItem::ACTION_CHECKLIST_ADD_ITEMS); // для добавления пункта чеклиста, разрешение стоит спрашивать у задачи, а не у чеклиста!
$item = new \CTaskCheckListItem($task, $itemId);
// удаление
$item->isActionAllowed(\CTaskCheckListItem::ACTION_REMOVE);
// сортировка
$item->isActionAllowed(\CTaskCheckListItem::ACTION_REORDER);
// изменение
$item->isActionAllowed(\CTaskCheckListItem::ACTION_MODIFY);
// выполнение
$item->isActionAllowed(\CTaskCheckListItem::ACTION_TOGGLE);Копировать
```

Новинки документации в соцсетях: