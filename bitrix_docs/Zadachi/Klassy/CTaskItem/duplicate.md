[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskItem](/api_help/tasks/classes/ctaskitem/index.php)

duplicate (С версии 14.5.11)

duplicate
=========

Включить вкладки

Описание и параметры

Пример использования

### Описание и параметры

```
CTaskItem[]
CTaskItem::duplicate(
	$overrideTaskData = array(),
	$parameters = array()
)Копировать
```

Метод копирует задачу или задачи.

#### Возвращаемое значение

Данный метод возвращает массив скопированных экземпляров класса [CTaskItem](/api_help/tasks/classes/ctaskitem/index.php).

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *$overrideTaskData* | Массив переопределяемых в копии задачи полей. |
| *$parameters* | Массив параметров задачи. |

### Пример использования

```
CModule::IncludeMOdule('tasks');
$task = new CTaskItem(1005, 1);
$res = $task->duplicate();
foreach($res as $taskInst)
{
	$data = $taskInst->getData(false);
	print($data['ID'].' -> '.$data['TITLE'].PHP_EOL);
}Копировать
```

Новинки документации в соцсетях: