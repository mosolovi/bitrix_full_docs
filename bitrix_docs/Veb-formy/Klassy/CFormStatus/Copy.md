[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormStatus](/api_help/form/classes/cformstatus/index.php)

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
CFormStatus::Copy(
	int status_id,
	string check_rights = "Y",
	mixed form_id = false
)Копировать
```

Копирует [статус](/api_help/form/terms.php#status). Возвращает ID нового [статуса](/api_help/form/terms.php#status) в случае положительного результата, в противном случае - "false". Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *status\_id* | ID [статуса](/api_help/form/terms.php#status) который необходимо скопировать. |
| *check\_rights* | Флаг необходимости проверки [прав](/api_help/form/terms.php#permissions) текущего пользователя. Возможны следующие значения:  * **Y** - права необходимо проверить; * **N** - право не нужно проверять.  Для копирования [статуса](/api_help/form/terms.php#status) необходимо обладать нижеследующими [правами](/api_help/form/terms.php#permissions#module):  1. **[25] просмотр параметров веб-формы** на ту веб-форму, из которой идет копирование; 2. **[30] полный доступ** на ту веб-форму, в которую копируется.  Параметр необязательный. По умолчанию - "Y" (права необходимо проверить). |
| *form\_id* | ID [веб-формы](/api_help/form/terms.php#form) в который необходимо скопировать [статус](/api_help/form/terms.php#status).  Необязательный параметр. По умолчанию - "false" (текущая [веб-форма](/api_help/form/terms.php#form)). |

### Смотрите также

* [CForm::Copy](/api_help/form/classes/cform/copy.php)
* [CFormField::Copy](/api_help/form/classes/cformfield/copy.php)
* [CFormAnswer::Copy](/api_help/form/classes/cformanswer/copy.php)

### Примеры использования

```
<?
$status_id = 1; // ID статуса
// скопируем статус
if ($NEW_STATUS_ID = CFormStatus::Copy($status_id))
{
	echo "Статус #1 успешно скопирован в новый статус #".$NEW_STATUS_ID;
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