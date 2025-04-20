[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskCheckListItem](/api_help/tasks/classes/ctaskchecklistitem/index.php)

setSortIndex (17.6.11)

setSortIndex
============

```
$task = \CTaskItem::getInstance($taskId, $userId);
$item = new \CTaskCheckListItem($task, $itemId);
$newIndex = 19;
$item->setSortIndex($newIndex);Копировать
```

Нестатический метод, изменяет индекс сортировки.

Новинки документации в соцсетях: