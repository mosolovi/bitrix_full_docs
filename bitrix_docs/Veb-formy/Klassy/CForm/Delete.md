[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CForm](/api_help/form/classes/cform/index.php)

Delete (3.1.1)

Delete
======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
bool
CForm::Delete(
	int form_id,
	string check_rights = "Y"
)Копировать
```

Удаляет [веб-форму](/api_help/form/terms.php#form) со всеми ее [результатами](/api_help/form/terms.php#result). Возвращает "true" в случае положительного результата, и "false" - в противном случае. Метод нестатический.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| *form\_id* | ID веб-формы. |  |
| *check\_rights* | Флаг необходимости проверки прав текущего пользователя. Возможны следующие значения:  * **Y** - права необходимо проверить; * **N** - право не нужно проверять.  Для удаления веб-формы необходимо иметь право **[W] Полный доступ на модуль "Веб-формы"**.  Параметр необязательный. По умолчанию - "Y" (права необходимо проверить). | 4.0.4 |

### Смотрите также

* [CFormField::Delete](/api_help/form/classes/cformfield/delete.php)
* [CFormAnswer::Delete](/api_help/form/classes/cformanswer/delete.php)
* [CFormStatus::Delete](/api_help/form/classes/cformstatus/delete.php)
* [CFormResult::Delete](/api_help/form/classes/cformresult/delete.php)

### Примеры использования

```
<?
$FORM_ID = 4;
// удалим веб-форму
if (CForm::Delete($FORM_ID))
{
	echo "Веб-форма #4 удалена.";
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