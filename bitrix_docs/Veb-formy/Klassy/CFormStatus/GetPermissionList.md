[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormStatus](/api_help/form/classes/cformstatus/index.php)

GetPermissionList (4.0.4)

GetPermissionList
=================

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
CFormStatus::GetPermissionList(
	int status_id,
	array &can_view, 
	array &can_move, 
	array &can_edit,
	array &can_delete
)Копировать
```

Возвращает массивы групп пользователей, имеющих определённые [права](/api_help/form/permissions.php#result) на указанный [статус](/api_help/form/terms.php#status). Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *status\_id* | ID [статуса](/api_help/form/terms.php#status). |
| *can\_view* | Ссылка на массив для хранения ID групп пользователей, обладающих правом на просмотр результата, находящемся в статусе *status\_id*. |
| *can\_move* | Ссылка на массив для хранения ID групп пользователей, обладающих правом перевода результатов в статус *status\_id*. |
| *can\_edit* | Ссылка на массив для хранения ID групп пользователей, обладающих правом редактирования результатов, находящихся в статусе *status\_id*. |
| *can\_edit* | Ссылка на массив для хранения ID групп пользователей, обладающих правом удаления результатов, находящихся в статусе *status\_id*. |

### Смотрите также

* [Права на результат](/api_help/form/permissions.php#result)
* [CForm::GetPermission](/api_help/form/classes/cform/getpermission.php)
* [CFormResult::GetPermissions](/api_help/form/classes/cformresult/getpermissions.php)

### Примеры использования

```
<?
$STATUS_ID = 1;
// получим массив групп обладающих определёнными правами на статус #1
CFormStatus::GetPermissionList($STATUS_ID, $arVIEW, $arMOVE, $arEDIT, $arDELETE);
// выведем массив групп обладающих правом 
// просмотра результатов находящихся в статусе #1
echo "<pre>"; print_r($arVIEW); echo "</pre>";
// выведем массив групп обладающих правом 
// перевода результатов в статус #1
echo "<pre>"; print_r($arMOVE); echo "</pre>";
// выведем массив групп обладающих правом 
// редактирования результатов находящихся в статусе #1
echo "<pre>"; print_r($arEDIT); echo "</pre>";
// выведем массив групп обладающих правом 
// удаления результатов находящихся в статусе #1
echo "<pre>"; print_r($arDELETE); echo "</pre>";
?>Копировать
```

Новинки документации в соцсетях: