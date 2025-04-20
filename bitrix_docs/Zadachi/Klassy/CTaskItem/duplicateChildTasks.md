[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskItem](/api_help/tasks/classes/ctaskitem/index.php)

duplicateChildTasks (С версии 14.5.11)

duplicateChildTasks
===================

Включить вкладки

Описание и параметры

Пример использования

### Описание и параметры

```
CTaskItem[]
CTaskItem::duplicateChildTasks(
	$cloneTaskInstance
)Копировать
```

Данный метод копирует подзадачи выбранной задачи.

#### Возвращаемое значение

Данный метод возвращает массив скопированных экземпляров класса [CTaskItem](/api_help/tasks/classes/ctaskitem/index.php).

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *$cloneTaskInstance* | Задача, подзадачи которой будут скопированы. |

### Пример использования

```
CModule::IncludeMOdule('tasks');
$donorTaskId = 1373;
$acceptorTaskId = 1379;
$executiveUserId = $GLOBALS['USER']->GetId();
// creating task instance
$donorTaskInstance = CTaskItem::getInstance($donorTaskId, $executiveUserId);
$acceptorTaskInstance = CTaskItem::getInstance($acceptorTaskId, $executiveUserId);
$subTasks = $donorTaskInstance-> duplicateChildTasks($acceptorTaskInstance);
print_r($subTasks);Копировать
```

Новинки документации в соцсетях: