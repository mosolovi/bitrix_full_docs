[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormResult](/api_help/form/classes/cformresult/index.php)

Delete (4.0.4)

Delete
======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
bool
CFormResult::Delete(
	int result_id,
	string check_rights = "Y"
)Копировать
```

Удаляет указанный [результат](/api_help/form/terms.php#result). В случае успеха метод возвращает "true", иначе - "false". Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *result\_id* | ID [результата](/api_help/form/terms.php#result). |
| *check\_rights* | Флаг необходимости проверки прав текущего пользователя. Возможны следующие значения:  * **Y** - права необходимо проверить; * **N** - права не нужно проверять.  Для успешного удаления [результата](/api_help/form/terms.php#result) необходимо обладать следующими [правами](/api_help/form/permissions.php):  1. На веб-форму, к которой принадлежит редактируемый результат:          **[20] Работа со всеми результатами в соответствии с их статусами**          или, в случае, если вы являетесь создателем удаляемого результата, достаточно права          **[15] Работа со своим результатом в соответствии с его статусом.** 2. На статус в котором находится редактируемый результат необходимо иметь право:          **[DELETE] удаление.**  Параметр необязательный. По умолчанию - "Y" (права необходимо проверить). |

### Смотрите также

* [CForm::Delete](/api_help/form/classes/cform/delete.php)
* [CFormField::Delete](/api_help/form/classes/cformfield/delete.php);
* [CFormAnswer::Delete](/api_help/form/classes/cformanswer/delete.php)
* [CFormStatus::Delete](/api_help/form/classes/cformstatus/delete.php)

### Примеры использования

```
<?
$RESULT_ID = 189; // ID результата
// удалим результат с проверкой прав текущего пользователя
if (CFormResult::Delete($RESULT_ID))
{
	echo "Результат # ".$RESULT_ID." успешно удален.";
}
else // ошибка
{
	global $strError;
	echo $strError;
}
?>Копировать
```

Новинки документации в соцсетях: