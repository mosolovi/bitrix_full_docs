[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskFilterCtrl](/api_help/tasks/classes/ctaskfilterctrl/index.php)

SwitchFilterPreset (12.0.1)

SwitchFilterPreset
==================

```
void
public function switchFilterPreset(
	$presetId
);
Копировать
```

Метод возвращает список имеющихся у пользователя предустановленных и пользовательских фильтров.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *$presetId* | Идентификатор фильтра, который следует сделать текущим. |

#### Возвращаемое значение

Нет.

#### Примеры использования

```
<?php
CModule::IncludeModule('tasks');
$userId = (int) $GLOBALS['USER']->getId();
$bGroupMode = false;
$oFilter = CTaskFilterCtrl::getInstance($userId, $bGroupMode);
// Делаем текущим фильтр «Все мои задачи»
$oFilter->switchFilterPreset(CTaskFilterCtrl::STD_PRESET_ALL_MY_TASKS);
$selectedFilter = $oFilter->getSelectedFilterPresetId();
echo $selectedFilter;	// Выведет число «-9», которое является значением константы  CTaskFilterCtrl::STD_PRESET_ALL_MY_TASKS
?>
Копировать
```

Новинки документации в соцсетях: