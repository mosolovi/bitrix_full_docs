[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormStatus](/api_help/form/classes/cformstatus/index.php)

GetPermissions (4.0.4)

GetPermissions
==============

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
array
CFormStatus::GetPermissions(
	int status_id
)Копировать
```

Возвращает массив [прав](/api_help/form/permissions.php#result) текущего пользователя на указанный [статус](/api_help/form/terms.php#status). В качестве значений данного массива допустимы:

* **VIEW** - право на просмотр [результатов](/api_help/form/terms.php#result) в данном статусе;
* **MOVE** - право на перевод результатов в данный статус;
* **EDIT** - право на редактирование результатов в данном статусе;
* **DELETE** - право на удаление результатов в данном статусе.

Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *status\_id* | ID [статуса](/api_help/form/terms.php#status). |

### Смотрите также

* [Права на результат](/api_help/form/permissions.php#result)
* [CForm::GetPermission](/api_help/form/classes/cform/getpermission.php)
* [CFormResult::GetPermissions](/api_help/form/classes/cformresult/getpermissions.php)

### Примеры использования

```
<?
$STATUS_ID = 1;
// получим права текущего пользователя для указанного статуса
$arPerm = CFormStatus::GetPermissions($STATUS_ID);
if (in_array("VIEW", $arPerm)) 
	echo "У вас есть право на просмотр результатов в данном статусе";
if (in_array("EDIT", $arPerm)) 
	echo "У вас есть право на редактирование результатов в данном статусе";
if (in_array("MOVE", $arPerm)) 
	echo "У вас есть право на установку данного статуса результатам";
if (in_array("DELETE", $arPerm)) 
	echo "У вас есть право на удаление результатов в данном статусе";
?>Копировать
```

Новинки документации в соцсетях: