[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskItem](/api_help/tasks/classes/ctaskitem/index.php)

complete (12.5.0)

complete
========

```
void 
public function complete();Копировать
```

Данный метод переводит задачу в статус *«завершена»* (**CTasks::STATE\_COMPLETED**) или *«условно завершена (ждет контроля исполнителя)»* (**CTasks::STATE\_SUPPOSEDLY\_COMPLETED**).

#### Пример

$ID = 1; // Ид нашей задачи

```
$test = new \Bitrix\Tasks\Item\Task($ID);
$test->complete();Копировать
```

Новинки документации в соцсетях: