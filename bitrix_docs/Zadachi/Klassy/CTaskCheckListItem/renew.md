[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskCheckListItem](/api_help/tasks/classes/ctaskchecklistitem/index.php)

renew (17.6.11)

renew
=====

```
$task = \CTaskItem::getInstance($taskId, $userId);
$item = new \CTaskCheckListItem($task, $itemId);
echo $item->renew();Копировать
```

Нестатический метод, помечает пункт чеклиста как невыполненный.

**Примечание**: В отличии от метода toggle, этот метод не переключает "выполненный"/"невыполненный", а принудительно выставляет “невыполненный”.

Новинки документации в соцсетях: