[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTasks](/api_help/tasks/classes/ctasks/index.php)

AddTags (10.0.2 - 12.0.9)

AddTags
=======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
void
CTasks::AddTags(
	ID,
	USER_ID,
	array arTags
);Копировать
```

Метод добавляет теги к задаче.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор задачи, к которой добавляются теги |
| USER\_ID | Идентификатор пользователя, добавившего теги |
| arTags | Массив идентификаторов задач |

#### Возвращаемое значение

Метод не имеет возвращаемого значения.

### Примеры использования

```
<?
if (CModule::IncludeModule("tasks"))
{
	$ID = 1;
	$USER_ID = 1;
	$arTags = array("javascript", "php", "css");
	CTasks::AddTags($ID, $USER_ID, $arTags);
}
?>Копировать
```

Новинки документации в соцсетях: