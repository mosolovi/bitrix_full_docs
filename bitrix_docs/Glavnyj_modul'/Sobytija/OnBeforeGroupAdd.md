[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnBeforeGroupAdd (с версии 9.5.8)

OnBeforeGroupAdd
================

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
bool
EventHandler(
	array &arFields
);Копировать
```

Событие вызывается в методе [CGroup::Add](/api_help/main/reference/cgroup/add.php) до добавления группы,
и может быть использовано для отмены добавления или переопределения некоторых полей.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arFields | Список полей ([класс CGroup](/api_help/main/reference/cgroup/index.php)) добавляемой группы пользователей. |

Параметр *arFields* данного обработчика является ссылкой на исходные переменные. Поэтому если изменить значение параметра внутри обработчика, это приведет к смене значения исходной переменной, поступившей на вход функции-обработчика.

#### Возвращаемое значение

Для отмены добавления группы и прекращении выполнения метода [CGroup::Add](/api_help/main/reference/cgroup/add.php) необходимо в функции-обработчике создать исключение методом $APPLICATION->[ThrowException()](/api_help/main/reference/cmain/throwexception.php) и вернуть *false*.

### Смотрите также

* [CGroup](/api_help/main/reference/cgroup/index.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Примеры использования

```
<?
AddEventHandler("main", "OnBeforeGroupAdd", "MyOnBeforeGroupAdd");
public static function MyOnBeforeGroupAdd(&$arFields)
{
	if($arFields["DESCRIPTION"] == '')
		$arFields["DESCRIPTION"] = "Описание группы";
}
?>Копировать
```

Новинки документации в соцсетях: