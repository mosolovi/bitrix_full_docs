[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskCheckListItem](/api_help/tasks/classes/ctaskchecklistitem/index.php)

moveAfterItem (17.6.11)

moveAfterItem
=============

```
$task = \CTaskItem::getInstance($taskId, $userId);
$item5 = new \CTaskCheckListItem($task, $itemId5);
$item2 = new \CTaskCheckListItem($task, $itemId2);
$item5->moveAfterItem($item2->getId());Копировать
```

Нестатический метод, перемещает пункт 5 под пункт 2 чеклиста.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| itemId | ID пункта чеклиста. |

Новинки документации в соцсетях: