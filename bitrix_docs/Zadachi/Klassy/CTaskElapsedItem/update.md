[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskElapsedItem](/api_help/tasks/classes/ctaskelapseditem/index.php)

update (12.5.4)

update
======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
void
public function update(
	array arFields,
);Копировать
```

Метод изменяет параметры указанной записи о затраченном времени.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| *arFields* | Массив, содержащий записи о времени и комментарии (**MINUTES** и **COMMENT\_TEXT**). | До 14.0.10 |
| *arFields* | Массив, содержащий записи о времени и комментарии (**SECONDS**, **COMMENT\_TEXT** и **CREATED\_DATE**). Допустимо использовать **MINUTES** вместо **SECONDS**, но нельзя их использовать одновременно. | с 14.0.10 |

#### Возвращаемое значение

При возникновении ошибки в исключениях будет содержаться текст ошибки.

### Примеры использования

```
$taskId = ...;
$itemId = ...;
$oTask = CTaskItem::getInstance($taskId, $USER->getId());
$oElapsedItem = new CTaskElapsedItem($oTask, $itemId);
$oElapsedItem->delete(); // $oElapsedItem->update($arFields); / $oElapsedItem->isActionAllowed($actionId);Копировать
```

Новинки документации в соцсетях: