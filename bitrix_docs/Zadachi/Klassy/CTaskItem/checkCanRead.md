[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskItem](/api_help/tasks/classes/ctaskitem/index.php)

checkCanRead

checkCanRead
============

```
CTaskItem::checkCanRead(
)Копировать
```

Метод проверяет доступ пользователя к задачам.

#### Параметры

Без параметров

#### Пример

```
$task = new CTaskItem(10, 3);
if (!$task->checkCanRead())
{
	print('Нет доступа к задаче c идентификатором 10 для пользователя с идентификатором 3');
}Копировать
```

Новинки документации в соцсетях: