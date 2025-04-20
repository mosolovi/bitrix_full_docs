[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskFilterCtrl](/api_help/tasks/classes/ctaskfilterctrl/index.php)

GetSelectedFilterPresetId (12.0.1)

GetSelectedFilterPresetId
=========================

```
int
public function getSelectedFilterPresetId();Копировать
```

Метод возвращает идентификатор текущего выбранного фильтра.

#### Возвращаемое значение

Возвращает идентификатор текущего выбранного фильтра.

#### Примеры использования

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