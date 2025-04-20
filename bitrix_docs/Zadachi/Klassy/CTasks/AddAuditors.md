[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTasks](/api_help/tasks/classes/ctasks/index.php)

AddAuditors (10.0.2 - 12.0.9)

AddAuditors
===========

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
void
CTasks::AddAuditors(
	ID,
	array arAuditors
);Копировать
```

Метод добавляет наблюдателей к задаче.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор задачи, к которой добавляются наблюдатели |
| arAuditors | Массив идентификаторов наблюдателей |

#### Возвращаемое значение

Метод не имеет возвращаемого значения.

### Примеры использования

```
<?
if (CModule::IncludeModule("tasks"))
{
	$ID = 1;
	$arAuditors = array(102, 34, 5);
	CTasks::AddAuditors($ID, $arAuditors);
}
?>Копировать
```

Новинки документации в соцсетях: