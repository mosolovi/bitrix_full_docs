[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskCheckListItem](/api_help/tasks/classes/ctaskchecklistitem/index.php)

add (17.6.11)

add
===

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
\CTaskCheckListItem::add(CTaskItemInterface $oTaskItem, array $arFields)
Копировать
```

Статический метод, отвечает за создание пункта чеклиста.

Первым параметром передается объект конкретной задачи, чтобы прикрепить к ней пункт чеклиста. Вторым параметром передается массив значений этого пункта чеклиста.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| arFields | **TITLE** (обязательный) - текст чеклиста. Можно передавать любую строку, кроме пустой строки или строки, содержащей только пробелы.    **Примечание:** Если **TITLE** будет равен **===** (трем знакам "равно"), то вместо пункта чеклиста будет разделительная линия.    **SORT\_INDEX** - индекс сортировки. целое число. Чем больше, тем ниже в списке.  **IS\_COMPLETE** - флаг о том, что пункт чеклиста уже выполнен. |

#### Возвращаемое значение

После успешного создания пункта чеклиста вернется объект \CTaskCheckListItem

### Примеры использования

```
$task = CTaskItem::getInstance($taskId, $userId);
\CTaskCheckListItem::add($task, ['TITLE'=>'First item', 'SORT_INDEX'=>10, 'IS_COMPLETE'=>'N']);
\CTaskCheckListItem::add($task, ['TITLE'=>'Second item', 'SORT_INDEX'=>20, 'IS_COMPLETE'=>'N']);
\CTaskCheckListItem::add($task, ['TITLE'=>'Third item. Completed', 'SORT_INDEX'=>30, 'IS_COMPLETE'=>'Y']);
Копировать
```

Новинки документации в соцсетях: