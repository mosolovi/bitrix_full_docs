[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskCheckListItem](/api_help/tasks/classes/ctaskchecklistitem/index.php)

isComplete (17.6.11)

isComplete
==========

```
$task = \CTaskItem::getInstance($taskId, $userId);
$item = new \CTaskCheckListItem($task, $itemId);
echo $item->iSComplete() ? 'Выполнен' : 'Не выполнен';Копировать
```

Нестатический метод, проверяет, выполнен ли пункт чеклиста.

Новинки документации в соцсетях: