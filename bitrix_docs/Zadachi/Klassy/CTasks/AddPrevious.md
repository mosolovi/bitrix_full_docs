[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTasks](/api_help/tasks/classes/ctasks/index.php)

AddPrevious (10.0.2 - 12.0.9)

AddPrevious
===========

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
void
CTasks::AddPrevious(
	ID,
	array arPrevious
);Копировать
```

Метод добавляет предыдущие задачи.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор задачи, к которой добавляются предыдущие задачи |
| arPrevious | Массив идентификаторов задач |

#### Возвращаемое значение

Метод не имеет возвращаемого значения.

### Примеры использования

```
<?
if (CModule::IncludeModule("tasks"))
{
	$ID = 1;
	$arPrevious = array(102, 34, 5);
	CTasks::AddPrevious($ID, $arPrevious);
}
?>Копировать
```

Новинки документации в соцсетях: