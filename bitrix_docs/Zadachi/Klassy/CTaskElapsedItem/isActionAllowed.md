[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskElapsedItem](/api_help/tasks/classes/ctaskelapseditem/index.php)

isActionAllowed (12.5.4)

isActionAllowed
===============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool 
public function isActionAllowed(
	int $actionId
);Копировать
```

Метод проверяет, разрешено ли действие?

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| *$actionId* | Идентификатор действия:  * **CTaskElapsedItem::ACTION\_ELAPSED\_TIME\_ADD**; * **CTaskElapsedItem::ACTION\_ELAPSED\_TIME\_MODIFY**; * **CTaskElapsedItem::ACTION\_ELAPSED\_TIME\_REMOVE**. |  |

#### Возвращаемое значение

Данный метод возвращает **true** если действие разрешено, иначе — **false**.

### Примеры использования

```
$taskId = ...;
$itemId = ...;
$oTask = CTaskItem::getInstance($taskId, $USER->getId());
$oElapsedItem = new CTaskElapsedItem($oTask, $itemId);
$oElapsedItem->isActionAllowed($actionId);Копировать
```

Новинки документации в соцсетях: