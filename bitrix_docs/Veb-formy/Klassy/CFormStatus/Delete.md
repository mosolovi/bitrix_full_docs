[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormStatus](/api_help/form/classes/cformstatus/index.php)

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
CFormStatus::Delete(
	int status_id,
	string check_rights = "Y"
)Копировать
```

Удаляет [статус](/api_help/form/terms.php#status). Возвращает "true" в случае положительного результата, и "false" - в противном случае. Метод нестатический.

**Примечание**  
Статусы, в которых находится хотя бы один [результат](/api_help/form/terms.php#result), невозможно удалить.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *status\_id* | ID удаляемого [статуса](/api_help/form/terms.php#status). |
| *check\_rights* | Флаг необходимости проверки [прав](/api_help/form/terms.php#permissions) текущего пользователя. Возможны следующие значения:  * **Y** - права необходимо проверить; * **N** - право не нужно проверять.  Для успешного выполнения удаления необходимо иметь [право](/api_help/form/terms.php#permissions#form) **[30] Полный доступ** на веб-форму, к которой принадлежит *status\_id*.  Параметр необязательный. По умолчанию - "Y" (права необходимо проверить). |

### Смотрите также

* [CForm::Delete](/api_help/form/classes/cform/delete.php)
* [CFormField::Delete](/api_help/form/classes/cformfield/delete.php)
* [CFormAnswer::Delete](/api_help/form/classes/cformanswer/delete.php)
* [CFormResult::Delete](/api_help/form/classes/cformresult/delete.php)

### Примеры использования

```
<?
$status_id = 1; // ID статуса
// удалим статус
if (CFormStatus::Delete($status_id))
{
	echo "Статус #1 успешно удален.";
}
else
{
	// выведем текст ошибки
	global $strError;
	echo $strError;
}
?>Копировать
```

Новинки документации в соцсетях: