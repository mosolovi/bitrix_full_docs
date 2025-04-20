[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormAnswer](/api_help/form/classes/cformanswer/index.php)

Delete (4.0.4)

Delete
======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CFormAnswer::Delete(
	int answer_id,
	int question_id = false,
)Копировать
```

Удаляет [ответ](/api_help/form/terms.php#answer) и все значения в результатах, связанные с ним. Возвращает "true" в случае положительного результата, и "false" - в противном случае. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *answer\_id* | ID удаляемого [ответа](/api_help/form/terms.php#answer). |
| *question\_id* | ID [вопроса](/api_help/form/terms.php#question), к которому приписан удаляемый [ответ](/api_help/form/terms.php#answer). Указание данного параметра позволяет ускорить выполнение функции.  Параметр необязательный. По умолчанию - "false". |

#### Смотрите также

* [CForm::Delete](/api_help/form/classes/cform/delete.php)
* [CFormField::Delete](/api_help/form/classes/cformfield/delete.php)
* [CFormStatus::Delete](/api_help/form/classes/cformstatus/delete.php)
* [CFormResult::Delete](/api_help/form/classes/cformresult/delete.php)

### Примеры использования

```
<?
$answer_id = 589; // ID ответа
// удалим ответ
if (CFormAnswer::Delete($answer_id))
{
	echo "Ответ #589 удален.";
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