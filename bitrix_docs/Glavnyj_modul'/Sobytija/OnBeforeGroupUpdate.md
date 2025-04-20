[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnBeforeGroupUpdate (с версии 9.5.8.)

OnBeforeGroupUpdate
===================

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
bool
EventHandler(
	int ID,
	array &arFields
);Копировать
```

Событие вызывается в методе [CGroup::Update](/api_help/main/reference/cgroup/update.php) до изменения полей группы,
и может быть использовано для отмены изменения или переопределения некоторых полей.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор изменяемой группы пользователей. |
| arFields | Список полей ([класс CGroup](/api_help/main/reference/cgroup/index.php)) изменяемой группы пользователей. |

Параметр *arFields* данного обработчика является ссылкой на исходные переменные. Поэтому если изменить значение параметра внутри обработчика, это приведет к смене значения исходной переменной, поступившей на вход функции-обработчика.

#### Возвращаемое значение

Для отмены изменения и прекращении выполнения метода [CGroup::Update](/api_help/main/reference/cgroup/update.php) необходимо в функции-обработчике создать исключение методом $APPLICATION->[ThrowException()](/api_help/main/reference/cmain/throwexception.php) и вернуть *false*.

### Смотрите также

* [CGroup](/api_help/main/reference/cgroup/index.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Примеры использования

```
<?
AddEventHandler("main", "OnBeforeGroupUpdate", "MyOnBeforeGroupUpdate");
public static function MyOnBeforeGroupUpdate($ID, &$arFields)
{
	if($ID == 1)
		$arFields["DESCRIPTION"] = "Главная группа админов.";
}
?>Копировать
```

Новинки документации в соцсетях: