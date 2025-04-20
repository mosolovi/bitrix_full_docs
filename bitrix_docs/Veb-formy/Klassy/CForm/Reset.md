[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CForm](/api_help/form/classes/cform/index.php)

Reset (3.1.1)

Reset
=====

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
bool
CForm::Reset(
	int form_id,
	string check_rights = "Y"
)Копировать
```

Удаляет все [результаты](/api_help/form/terms.php#result) [веб-формы](/api_help/form/terms.php#form). Возвращает "true" в случае положительного результата, и "false" - в противном случае. Метод нестатический.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| *form\_id* | ID веб-формы. |  |
| *check\_rights* | Флаг необходимости проверки [прав](/api_help/form/terms.php#permissions) текущего пользователя. Возможны следующие значения:  * **Y** - права необходимо проверить; * **N** - право не нужно проверять.  Для удаления всех результатов веб-формы необходимо иметь [право](/api_help/form/terms.php#permissions#form) **[30] Полный доступ** на форму, указанную в параметре *form\_id*.   Параметр необязательный. По умолчанию - "Y" (права необходимо проверить). | 4.0.4 |

### Смотрите также

* [CFormField::Reset](/api_help/form/classes/cformfield/reset.php)
* [CFormResult::Reset](/api_help/form/classes/cformresult/reset.php)

### Примеры использования

```
<?
$FORM_ID = 4;
// удалим результаты веб-формы
if (CForm::Reset($FORM_ID))
{
	echo "Результаты веб-формы #4 удалены.";
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