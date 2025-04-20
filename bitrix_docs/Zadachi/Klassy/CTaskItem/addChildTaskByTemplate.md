[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskItem](/api_help/tasks/classes/ctaskitem/index.php)

addChildTaskByTemplate (С версии 14.5.11)

addChildTaskByTemplate
======================

Включить вкладки

Описание и параметры

Пример использования

### Описание и параметры

```
CTaskItem[]
CTaskItem::addChildTasksByTemplate(
	$templateId, 
	$parameters = array()
)Копировать
```

Метод добавляет подзадачи из шаблона.

#### Возвращаемое значение

Данный метод возвращает массив созданных экземпляров класса [CTaskItem](/api_help/tasks/classes/ctaskitem/index.php).

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *$templateId* | ID шаблона. |
| *$parameters* | Массив параметров подзадачи. |

### Пример использования

```
CModule::IncludeModule('tasks');
$taskId = 1373;
$executiveUserId = $GLOBALS['USER']->GetId();
$templateId = 6;
// creating task instance to attach new subtasks to
$taskInstance = CTaskItem::getInstance($taskId, $executiveUserId);
$createdSubtasks = $taskInstance->addChildTasksByTemplate($templateId, array(
	// transfer some parameters
	'BEFORE_ADD_CALLBACK' => function(&$fields){
		print('will be created:'.PHP_EOL);
		print_r($fields);
	},
));
print_r($createdSubtasks);Копировать
```

Новинки документации в соцсетях: