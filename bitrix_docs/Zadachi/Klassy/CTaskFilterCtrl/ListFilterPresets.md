[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskFilterCtrl](/api_help/tasks/classes/ctaskfilterctrl/index.php)

ListFilterPresets (12.0.1)

ListFilterPresets
=================

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
array
public function listFilterPresets(
	$bTreeMode = false
);Копировать
```

Метод возвращает список имеющихся у пользователя предустановленных и пользовательских фильтров.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *$bTreeMode* | Задает формат возвращаемого списка фильтров. Если **true** — результат будет в виде дерева, при **false** — просто список фильтров. |

#### Возвращаемое значение

Возвращает массив, описывающий список фильтров. Каждый элемент фильтра описан отдельным массивом с ключами:

* **Name** - имя фильтра;
* **Parent** - идентификатор родительского фильтра, **NULL** — для корневого родительского фильтра;
* **Condition** - сериализованное (с помощью функции **serialize()**) значение условий фильтра.
* **#Children** (при режиме `$bTreeMode = true`) - ключ присутствует в фильтрах, имеющих дочерние фильтры. Содержит массив фильтров.

Пример возвращаемого массива см. ниже.

### Примеры использования

```
<?php
CModule::IncludeModule('tasks');
$userId = (int) $GLOBALS['USER']->getId();
$bGroupMode = false;
$oFilter = CTaskFilterCtrl::getInstance($userId, $bGroupMode);
$arPresets1 = $oFilter->listFilterPresets();
var_dump($arPresets1);
$arPresets2 = $oFilter->listFilterPresets(true);	// в формате дерева
var_dump($arPresets2);
?>
Вывод для $arPresets1: 
array(10) {
	[0]=>
	array(3) {
		["Name"]=>
		string(1) "/"
		["Parent"]=>
		NULL
		["Condition"]=>
		NULL
	}
	[-1]=>
	array(3) {
		["Name"]=>
		string(10) "Мои задачи"
		["Parent"]=>
		int(0)
		["Condition"]=>
		string(116) "a:3:{s:7:"::LOGIC";s:3:"AND";s:6:"MEMBER";i:1;s:6:"STATUS";a:6:{i:0;i:-2;i:1;i:-1;i:2;i:1;i:3;i:2;i:4;i:3;i:5;i:7;}}"
	}
	[-2]=>
	array(3) {
		["Name"]=>
		string(16) "Поставленные мне"
		["Parent"]=>
		int(-1)
		["Condition"]=>
		string(114) "a:3:{s:7:"::LOGIC";s:3:"AND";s:4:"DOER";i:1;s:6:"STATUS";a:6:{i:0;i:-2;i:1;i:-1;i:2;i:1;i:3;i:2;i:4;i:3;i:5;i:7;}}"
	}, ...
Вывод для $arPresets2: 
array(4) {
	[-1]=>
	array(4) {
		["Name"]=>
		string(10) "Мои задачи"
		["Parent"]=>
		int(0)
		["Condition"]=>
		string(116) "a:3:{s:7:"::LOGIC";s:3:"AND";s:6:"MEMBER";i:1;s:6:"STATUS";a:6:{i:0;i:-2;i:1;i:-1;i:2;i:1;i:3;i:2;i:4;i:3;i:5;i:7;}}"
		["#Children"]=>
		array(3) {
			[-2]=>
			array(4) {
				["Name"]=>
				string(16) "Поставленные мне"
				["Parent"]=>
				int(-1)
				["Condition"]=>
				string(114) "a:3:{s:7:"::LOGIC";s:3:"AND";s:4:"DOER";i:1;s:6:"STATUS";a:6:{i:0;i:-2;i:1;i:-1;i:2;i:1;i:3;i:2;i:4;i:3;i:5;i:7;}}"
				["#Children"]=>
				array(2) {
					[-7]=>
					array(3) {
						["Name"]=>
						string(15) "Я ответственный"
						["Parent"]=>
						int(-2)
						["Condition"]=>
						string(125) "a:3:{s:7:"::LOGIC";s:3:"AND";s:14:"RESPONSIBLE_ID";i:1;s:6:"STATUS";a:6:{i:0;i:-2;i:1;i:-1;i:2;i:1;i:3;i:2;i:4;i:3;i:5;i:7;}}"
					}
					[-8]=>
					array(3) {
						["Name"]=>
						string(15) "Я соисполнитель"
						["Parent"]=>
						int(-2)
						["Condition"]=>
						string(121) "a:3:{s:7:"::LOGIC";s:3:"AND";s:10:"ACCOMPLICE";i:1;s:6:"STATUS";a:6:{i:0;i:-2;i:1;i:-1;i:2;i:1;i:3;i:2;i:4;i:3;i:5;i:7;}}"
					}
				}
			}, ...Копировать
```

Новинки документации в соцсетях: