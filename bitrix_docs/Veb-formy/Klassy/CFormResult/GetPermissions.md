[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormResult](/api_help/form/classes/cformresult/index.php)

GetPermissions (3.3.10)

GetPermissions
==============

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
array
CFormResult::GetPermissions(
	int result_id,
	int ¤t_status_id
)Копировать
```

Возвращает массив символьных обозначений [прав](/api_help/form/permissions.php), которыми обладает текущий пользователь для указанного [результата](/api_help/form/terms.php#result). Помимо этого, метод возвращает ID [статуса](/api_help/form/terms.php#status) в котором находится указанный результат. Метод нестатический.

В результирующем массиве могут быть следующие символьные обозначения прав:

* **VIEW** - право на просмотр результата;
* **EDIT** - право на редактирование результата;
* **DELETE** - право на удаление результата.

**Примечание**  
Права на результат, по сути, являются правами на статус, в котором находится данный результат.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *result\_id* | ID [результата](/api_help/form/terms.php#result). |
| *current\_status\_id* | Ссылка на переменную, в которую будет сохранен ID [статуса](/api_help/form/terms.php#status), указанного результата *result\_id*. |

### Смотрите также

* [Права на результат](/api_help/form/permissions.php#result)
* [CFormStatus::GetPermissions](/api_help/form/classes/cformstatus/getpermissions.php)
* [CFormStatus::GetPermissionList](/api_help/form/classes/cformstatus/getpermissionlist.php)
* [CForm::GetPermission](/api_help/form/classes/cform/getpermission.php)

### Примеры использования

```
<?
$RESULT_ID = 189; // ID результата
// получим массив прав
$arPerm = CFormResult::GetPermissions($RESULT_ID, $current_status_id);
echo "Результат #".$RESULT_ID." находится в статусе ".$current_status_id;
if (in_array("VIEW", $arPerm)) 
	echo "У вас есть право на просмотр результата #".$RESULT_ID;
if (in_array("EDIT", $arPerm)) 
	echo "У вас есть право на редактирование результата #".$RESULT_ID;
if (in_array("DELETE", $arPerm)) 
	echo "У вас есть право на удаление результата #".$RESULT_ID;
?>Копировать
```

Новинки документации в соцсетях: