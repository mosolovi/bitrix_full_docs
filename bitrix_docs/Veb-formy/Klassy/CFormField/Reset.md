[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormField](/api_help/form/classes/cformfield/index.php)

Reset (4.0.4)

Reset
=====

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
bool
CFormField::Reset(
	int field_id,
	string check_rights = "Y"
)Копировать
```

Удаляет все значения ответов из [результатов](/api_help/form/terms.php#result) по заданному [вопросу](/api_help/form/terms.php#question)/[полю](/api_help/form/terms.php#field). Возвращает "true" в случае положительного результата, и "false" - в противном случае. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *field\_id* | ID [вопроса](/api_help/form/terms.php#question)/[поля](/api_help/form/terms.php#field). |
| *check\_rights* | Флаг необходимости проверки [прав](/api_help/form/terms.php#permissions) текущего пользователя. Возможны следующие значения:  * **Y** - права необходимо проверить; * **N** - право не нужно проверять.  Для успешного выполнения данной операции необходимо иметь [право](/api_help/form/terms.php#permissions#form) **[30] Полный доступ** на веб-форму, к которой принадлежит *field\_id*.   Параметр необязательный. По умолчанию - "Y" (права необходимо проверить). |

### Смотрите также

* [CForm::Reset](/api_help/form/classes/cform/reset.php)
* [CFormResult::Reset](/api_help/form/classes/cformresult/reset.php)

### Примеры использования

```
<?
$FIELD_ID = 4;
// удалим все ответы из результатов на вопрос с ID=140
if (CFormField::Reset($FIELD_ID))
{
	echo "Операция успешна.";
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