[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CCourse](/api_help/learning/classes/ccourse/index.php)

GetGroupPermissions (доступен с 5.0.3)

GetGroupPermissions
===================

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
array
CCourse::GetGroupPermissions(
	int COURSE_ID
);Копировать
```

Возвращает права доступа к учебному курсу с идентификатором COURSE\_ID для всех групп пользователей. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| COURSE\_ID | Идентификатор курса. |

#### Возвращаемое значение

Массив прав вида Array("ID группы"=>"Право доступа"[, ...]). Право доступа может принимать значение: "D" - запрещён, "R" - чтение, "W" - изменение, "X" - полный доступ (изменение + право изменять права доступа).

#### Смотрите также

* [CCourse](/api_help/learning/classes/ccourse/index.php)::[GetPermission](/api_help/learning/classes/ccourse/getpermission.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$arPerm = CCourse::GetGroupPermissions($COURSE = 8);
	print_r($arPerm);
	/*
	The above example will output something similar to:
	Array
	(
		[2] => R
		[22] => W
	)
	*/
}
?>Копировать
```

Новинки документации в соцсетях: