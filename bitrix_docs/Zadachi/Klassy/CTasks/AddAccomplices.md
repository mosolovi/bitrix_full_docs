[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTasks](/api_help/tasks/classes/ctasks/index.php)

AddAccomplices (10.0.2 - 12.0.9)

AddAccomplices
==============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
void
CTasks::AddAccomplices(
	ID,
	array arAccomplices
);Копировать
```

Метод добавляет соисполнителей к задаче.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор задачи, к которой добавляются соисполнители |
| arAccomplices | Массив идентификаторов исполнителей |

#### Возвращаемое значение

Метод не имеет возвращаемого значения.

### Примеры использования

```
<?
if (CModule::IncludeModule("tasks"))
{
	$ID = 1;
	$arAccomplices = array(102, 34, 5);
	CTasks::AddAccomplices($ID, $arAccomplices);
}
?>Копировать
```

Новинки документации в соцсетях: