[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskFilterCtrl](/api_help/tasks/classes/ctaskfilterctrl/index.php)

GetSelectedFilterPresetName (12.0.1)

GetSelectedFilterPresetName
===========================

```
string
public function getSelectedFilterPresetName();
Копировать
```

Метод возвращает название текущего выбранного фильтра.

#### Возвращаемое значение

Возвращает название текущего выбранного фильтра.

#### Примеры использования

```
<?php
CModule::IncludeModule('tasks');
$userId = (int) $GLOBALS['USER']->getId();
$bGroupMode = false;
$oFilter = CTaskFilterCtrl::getInstance($userId, $bGroupMode);
echo $oFilter->getSelectedFilterPresetName(); // Выведет, к примеру, «Созданные мной»
?>
Копировать
```

Новинки документации в соцсетях: