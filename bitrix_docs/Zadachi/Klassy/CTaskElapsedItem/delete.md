[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskElapsedItem](/api_help/tasks/classes/ctaskelapseditem/index.php)

delete (12.5.4)

delete
======

```
void
public function delete();Копировать
```

Метод удаляет запись о затраченном времени.

**Примеры использования**

```
$taskId = ...;
$itemId = ...;
$oTask = CTaskItem::getInstance($taskId, $USER->getId());
$oElapsedItem = new CTaskElapsedItem($oTask, $itemId);
$oElapsedItem->delete();Копировать
```

Новинки документации в соцсетях: