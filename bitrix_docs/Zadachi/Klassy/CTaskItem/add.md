[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskItem](/api_help/tasks/classes/ctaskitem/index.php)

add (С версии 12.5.3)

add
===

Включить вкладки

Описание и параметры

Примеры

### Описание и параметры

```
CTaskItem
public static function add(
	$arNewTaskData,
	$userId
);Копировать
```

Данный метод возвращает экземпляр класса **CTaskItem**.

**Примечание:** Метод принимает массив конфигурационных параметров и генерирует скрипты, необходимые для показа файлового диалога. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *$arNewTaskData* | Массив полей данных по задаче (**TITLE**, **DESCRIPTION** и т.д.), список полей - аналогично методу **CTasks::Add()**. |
| *$userId* | Идентификатор пользователя, от имени которого будут проверяться права и правила бизнес-логики. |

### Примеры

```
$task = new \Bitrix\Tasks\Item\Task(); // создание экземпляра новой сущности (например, новой задачи, которой еще нет в базе данных)
$task = new \Bitrix\Tasks\Item\Task(0, 1); // создание экземпляра новой сущности из под пользователя 1Копировать
```

Затем

```
$task->title = 'hello';
$task->responsibleId = 4;Копировать
```

Либо

```
$task['TITLE'] = 'hello';
$task['RESPONSIBLE_ID'] = 4;Копировать
```

Затем

```
$result = $task->save();
if($result->isSuccess())
{
	print('EEEEEhaaaa!!!');
}
else
{
	print('NoEEEEEhaaaa!!!:');
	print_r($result->dump());
}Копировать
```

Новинки документации в соцсетях: