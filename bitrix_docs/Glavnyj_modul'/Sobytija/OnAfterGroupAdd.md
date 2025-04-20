[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnAfterGroupAdd (с версии 9.5.8)

OnAfterGroupAdd
===============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
EventHandler(
	array &arFields
);Копировать
```

Событие вызывается в методе [CGroup::Add](/api_help/main/reference/cgroup/add.php) после добавления группы,
и может быть использовано для действий, связанных с группой.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arFields | Список полей ([класс CGroup](/api_help/main/reference/cgroup/index.php)) добавляемой группы пользователей. Массив содержит в том числе ключ *ID* с идентификатором добавленной группы. |

#### Возвращаемое значение

Не используется.

#### Смотрите также

* [CGroup](/api_help/main/reference/cgroup/index.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Примеры использования

```
<?
AddEventHandler("main", "OnAfterGroupAdd", "MyOnAfterGroupAdd");
public static function MyOnAfterGroupAdd(&$arFields)
{
	AddMessage2Log(print_r($arFields, true));
}
?>Копировать
```

Новинки документации в соцсетях: