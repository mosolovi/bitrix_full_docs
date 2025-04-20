[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CCourse](/api_help/learning/classes/ccourse/index.php)

GetPermission (доступен с 5.0.3)

GetPermission
=============

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
string
CCourse::GetPermission(
	int courseId
);Копировать
```

Возвращает право доступа к учебному курсу с идентификатором *courseId* для текущего пользователя. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| courseId | Идентификатор курса.    До версии 12.0.0 параметр назывался COURSE\_ID. |

#### Возвращаемое значение

Символ права доступа: "D" - запрещён, "R" - чтение, "W" - изменение, "X" - полный доступ (изменение + право изменять права доступа).

### Смотрите также

* [CCourse](/api_help/learning/classes/ccourse/index.php)::[SetPermission](/api_help/learning/classes/ccourse/setpermission.php)
* [CCourse](/api_help/learning/classes/ccourse/index.php)::[GetGroupPermissions](/api_help/learning/classes/ccourse/getgrouppermissions.php)

### Примеры использования

```
<?
$permission = CCourse::GetPermission($id);
if ($permission<"X")
	return false;
?>Копировать
```

Новинки документации в соцсетях: