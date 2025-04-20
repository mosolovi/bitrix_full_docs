[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CForm](/api_help/form/classes/cform/index.php)

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
CForm::Copy(
	int form_id,
	string check_rights = "Y"
)Копировать
```

Копирует [веб-форму](/api_help/form/terms.php#form) с ее [вопросами](/api_help/form/terms.php#question), [полями](/api_help/form/terms.php#field) и [статусами](/api_help/form/terms.php#status). Возвращает ID новой веб-формы в случае положительного результата, в противном случае - "false". Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *form\_id* | ID формы. |
| *check\_rights* | Флаг необходимости проверки прав текущего пользователя. Возможны следующие значения:  * **Y** - права необходимо проверить; * **N** - право не нужно проверять.  Для копирования веб-формы необходимо право **[W] Полный доступ" на модуль "Веб-формы****"**.  Параметр необязательный. По умолчанию - "Y" (права необходимо проверить). |

### Смотрите также

* [CFormField::Copy](/api_help/form/classes/cformfield/copy.php)
* [CFormAnswer::Copy](/api_help/form/classes/cformanswer/copy.php)
* [CFormStatus::Copy](/api_help/form/classes/cformstatus/copy.php)

### Примеры использования

```
<?
$FORM_ID = 4;
// скопируем веб-форму
if ($NEW_FORM_ID=CForm::Copy($FORM_ID))
{
	echo "Веб-форма #4 успешно скопирована в новую веб-форму #".$NEW_FORM_ID;
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