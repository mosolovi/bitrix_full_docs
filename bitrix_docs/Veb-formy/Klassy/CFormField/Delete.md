[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormField](/api_help/form/classes/cformfield/index.php)

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
CFormField::Delete(
	int field_id,
	string check_rights = "Y"
)Копировать
```

Удаляет [вопрос](/api_help/form/terms.php#question)/[поле](/api_help/form/terms.php#field) и все ответы на него из [результатов](/api_help/form/terms.php#result). Возвращает "true" в случае положительного результата, и "false" - в противном случае. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *field\_id* | ID [вопроса](/api_help/form/terms.php#question)/[поля](/api_help/form/terms.php#field). |
| *check\_rights* | Флаг необходимости проверки [прав](/api_help/form/terms.php#permissions) текущего пользователя. Возможны следующие значения:  * **Y** - права необходимо проверить; * **N** - право не нужно проверять.  Для успешного выполнения данной операции необходимо иметь [право](/api_help/form/terms.php#permissions#form) **[30] Полный доступ** на веб-форму, к которой принадлежит *field\_id*.   Параметр необязательный. По умолчанию - "Y" (права необходимо проверить). |

### Смотрите также

* [CForm::Delete](/api_help/form/classes/cform/delete.php)
* [CFormAnswer::Delete](/api_help/form/classes/cformanswer/delete.php)
* [CFormStatus::Delete](/api_help/form/classes/cformstatus/delete.php)
* [CFormResult::Delete](/api_help/form/classes/cformresult/delete.php)

### Примеры использования

```
<?
$FIELD_ID = 140;
// удалим вопрос #140
if (CFormField::Delete($FIELD_ID))
{
	echo "Вопрос #140 удален.";
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