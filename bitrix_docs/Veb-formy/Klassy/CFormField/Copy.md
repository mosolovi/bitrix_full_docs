[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormField](/api_help/form/classes/cformfield/index.php)

Copy (4.0.4)

Copy
====

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
mixed
CFormField::Copy(
	int field_id,
	string check_rights = "Y",
	mixed form_id = false
)Копировать
```

Копирует [вопрос](/api_help/form/terms.php#question) или [поле](/api_help/form/terms.php#field) веб-формы. Возвращает ID нового [вопроса](/api_help/form/terms.php#question)/[поля](/api_help/form/terms.php#field) в случае положительного результата, в противном случае - "false". Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *field\_id* | ID [вопроса](/api_help/form/terms.php#question)/[поля](/api_help/form/terms.php#field), который необходимо скопировать. |
| *check\_rights* | Флаг необходимости проверки [прав](/api_help/form/terms.php#permissions) текущего пользователя. Возможны следующие значения:  * **Y** - права необходимо проверить; * **N** - право не нужно проверять.  Для копирования [вопроса](/api_help/form/terms.php#question)/[поля](/api_help/form/terms.php#field) необходимо обладать нижеследующими [правами](/api_help/form/terms.php#permissions#module):  1. **[25] просмотр параметров веб-формы** на веб-форму, из которой идет копирование; 2. **[30] полный доступ** на веб-форму, в которую копируется  Параметр необязательный. По умолчанию - "Y" (права необходимо проверить). |
| *form\_id* | ID веб-формы, в которую необходимо скопировать [вопрос](/api_help/form/terms.php#question)/[поле](/api_help/form/terms.php#field).   Необязательный параметр. По умолчанию - "false" (текущая веб-форма). |

### Смотрите также

* [CForm::Copy](/api_help/form/classes/cform/copy.php)
* [CFormAnswer::Copy](/api_help/form/classes/cformanswer/copy.php)
* [CFormStatus::Copy](/api_help/form/classes/cformstatus/copy.php)

### Примеры использования

```
<?
$FIELD_ID = 140; // ID вопроса
// скопируем вопрос
if ($NEW_FIELD_ID=CFormField::Copy($FIELD_ID))
{
	echo "Вопрос #140 успешно скопирован в новый вопрос #".$NEW_FIELD_ID;
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