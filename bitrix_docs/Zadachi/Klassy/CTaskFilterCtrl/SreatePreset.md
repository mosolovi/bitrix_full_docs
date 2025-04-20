[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskFilterCtrl](/api_help/tasks/classes/ctaskfilterctrl/index.php)

СreatePreset (12.0.1)

СreatePreset
============

```
int
public function createPreset(
	$arPresetData
);
Копировать
```

Метод возвращает идентификатор созданного пресета.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *$arPresetData* | Массив, описывающий пресет. Должен содержать следующие ключи:  * **Name** — имя пресета (до 100 символов), * **Parent** — идентификатор родительского пресета (должен быть равен **CTaskFilterCtrl::ROOT\_PRESET**), * **Condition** — массив, описывающий условие фильтра (соответствует тому, что можно передавать в качества параметра **$arFilter** в метод **CTasks::GetList()**). |

Новинки документации в соцсетях: