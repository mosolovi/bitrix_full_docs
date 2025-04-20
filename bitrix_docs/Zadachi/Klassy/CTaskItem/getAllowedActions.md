[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskItem](/api_help/tasks/classes/ctaskitem/index.php)

getAllowedActions (С версии 12.5.8)

getAllowedActions
=================

```
array
public function getAllowedActions(
	$bReturnAsStrings = false
);Копировать
```

Данный метод возвращает массив, описывающий допустимые действия над задачей.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *$bReturnAsStrings* | Если **false** (по умолчанию), то возвращается массив идентификаторов допустимых действий (константы **CTaskItem::ACTION\_\***), иначе ассоциативный массив, ключами которого являются названия действий (совпадают с названиями констант), а значениями — *true* (действие разрешено) или *false* (действие запрещено). |

Пример возвращаемого значения при **$bReturnAsStrings === false**:

```
array(7) {
	[0]=>
	int(9)
	[1]=>
	int(8)
	[2]=>
	int(3)
	[3]=>
	int(6)
	[4]=>
	int(7)
	[5]=>
	int(10)
	[7]=>
	int(13)
}Копировать
```

Пример возвращаемого значения при **$bReturnAsStrings === true**:

```
array(12) {
	["ACTION_ACCEPT"]=>
	bool(false)
	["ACTION_DECLINE"]=>
	bool(false)
	["ACTION_COMPLETE"]=>
	bool(true)
	["ACTION_APPROVE"]=>
	bool(false)
	["ACTION_DISAPPROVE"]=>
	bool(false)
	["ACTION_START"]=>
	bool(true)
	["ACTION_DELEGATE"]=>
	bool(true)
	["ACTION_REMOVE"]=>
	bool(true)
	["ACTION_EDIT"]=>
	bool(true)
	["ACTION_DEFER"]=>
	bool(true)
	["ACTION_RENEW"]=>
	bool(false)
	["ACTION_CREATE"]=>
	bool(false)
}Копировать
```

Новинки документации в соцсетях: