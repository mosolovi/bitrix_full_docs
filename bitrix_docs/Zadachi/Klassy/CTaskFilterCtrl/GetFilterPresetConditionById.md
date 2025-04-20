[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskFilterCtrl](/api_help/tasks/classes/ctaskfilterctrl/index.php)

GetFilterPresetConditionById (12.0.1)

GetFilterPresetConditionById
============================

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
string
public function getFilterPresetConditionById(
	$presetId
);Копировать
```

Метод возвращает условие фильтра с заданным идентификатором.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *$presetId* | Идентификатор фильтра, по которому запрашивается условие. |

#### Возвращаемое значение

Возвращает условие фильтра с заданным идентификатором в виде массива, который можно передать в качестве параметра **$arFilter** в метод **CTasks::GetList()**.

### Примеры использования

```
<?php
CModule::IncludeModule('tasks');
$userId = (int) $GLOBALS['USER']->getId();
$bGroupMode = false;
$oFilter = CTaskFilterCtrl::getInstance($userId, $bGroupMode);
$selectedFilter = $oFilter->getSelectedFilterPresetId();
$arFilter = $oFilter->getFilterPresetConditionById($selectedFilter);
// Покажем условия фильтра
var_dump($arFilter);
// Это условие можно использовать в CTasks::GetList();
$rsTasks = CTasks::GetList(array(), $arFilter);
?>
Выведет:
array(1) {
	["::SUBFILTER-ROOT"]=>
	array(3) {
		["::LOGIC"]=>
		string(3) "AND"
		["MEMBER"]=>
		int(1)
		["STATUS"]=>
		array(6) {
			[0]=>
			int(-2)
			[1]=>
			int(-1)
			[2]=>
			int(1)
			[3]=>
			int(2)
			[4]=>
			int(3)
			[5]=>
			int(7)
		}
	}
}Копировать
```

Новинки документации в соцсетях: