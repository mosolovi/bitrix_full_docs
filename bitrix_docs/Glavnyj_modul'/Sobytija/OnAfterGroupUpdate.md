[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnAfterGroupUpdate (с версии 9.5.8)

OnAfterGroupUpdate
==================

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
void
EventHandler(
	int ID,
	array &arFields
);Копировать
```

Событие вызывается в методе [CGroup::Update](/api_help/main/reference/cgroup/update.php) после изменения полей группы,
и может быть использовано для дополнительных действий, связанных с группой.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор измененной группы пользователей. |
| arFields | Список полей ([класс CGroup](/api_help/main/reference/cgroup/index.php)) измененной группы пользователей. |

#### Возвращаемое значение

Не используется.

#### Смотрите также

* [CGroup](/api_help/main/reference/cgroup/index.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Примеры использования

```
<?
AddEventHandler("main", "OnAfterGroupUpdate", "MyOnAfterGroupUpdate");
public static function MyOnAfterGroupUpdate($ID, &$arFields)
{
	if($ID == 1)
		AddMessage2Log(print_r($arFields, true));
}
?>Копировать
```

Новинки документации в соцсетях: