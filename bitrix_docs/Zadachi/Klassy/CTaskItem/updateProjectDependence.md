[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskItem](/api_help/tasks/classes/ctaskitem/index.php)

updateProjectDependence

updateProjectDependence
=======================

```
CTaskItem::updateProjectDependence(
	$parentId,
	$linkType = DependenceTable::LINK_TYPE_FINISH_START
);Копировать
```

Обновляет зависимость одной задачи от другой в рамках Ганта.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| parentId | INT - задача, к которой добавляется зависимость |
| *linkType* | INT вида связи. По умолчанию 2. Меняется от 0 до 3 в зависимости от того, какой вид связи необходим. |

#### Примеры использования

```
$task = CTaskItem::getInstance(1, 1);
$task->updateProjectDependence(2, \Bitrix\Tasks\Task\DependenceTable::LINK_TYPE_FINISH_FINISH);Копировать
```

Новинки документации в соцсетях: