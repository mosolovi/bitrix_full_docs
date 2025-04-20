[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskFilterCtrl](/api_help/tasks/classes/ctaskfilterctrl/index.php)

GetSelectedFilterPresetCondition (12.0.1)

GetSelectedFilterPresetCondition
================================

```
array
public function getSelectedFilterPresetCondition();
Копировать
```

Метод возвращает условие текущего выбранного фильтра.

#### Возвращаемое значение

Возвращает условие текущего выбранного фильтра в виде массива, который можно передать в качестве параметра **$arFilter** в метод **CTasks::GetList()**;

#### Примеры использования

```
<?php
CModule::IncludeModule('tasks');
$userId = (int) $GLOBALS['USER']->getId();
$bGroupMode = false;
$oFilter = CTaskFilterCtrl::getInstance($userId, $bGroupMode);
$arFilter = $oFilter->getSelectedFilterPresetCondition();
// Покажем условия фильтра
var_dump($arFilter);
// Это условие можно использовать в CTasks::GetList();
$rsTasks = CTasks::GetList(array(), $arFilter);
?>
Копировать
```

Новинки документации в соцсетях: