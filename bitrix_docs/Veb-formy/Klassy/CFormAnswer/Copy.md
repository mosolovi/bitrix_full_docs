[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormAnswer](/api_help/form/classes/cformanswer/index.php)

Copy (4.0.4)

Copy
====

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
mixed
CFormAnswer::Copy(
	int answer_id,
	mixed question_id = false
)Копировать
```

Копирует [ответ](/api_help/form/terms.php#answer). Возвращает ID нового [ответа](/api_help/form/terms.php#answer) в случае положительного результата, в противном случае - "false". Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *answer\_id* | ID [ответа](/api_help/form/terms.php#answer) который необходимо скопировать. |
| *question\_id* | ID [вопроса](/api_help/form/terms.php#question), в который необходимо скопировать [ответ](/api_help/form/terms.php#answer).  Необязательный параметр. По умолчанию - "false" (текущий [вопрос](/api_help/form/terms.php#question)). |

#### Смотрите также

* [CForm::Copy](/api_help/form/classes/cform/copy.php)
* [CFormField::Copy](/api_help/form/classes/cformfield/copy.php)
* [CFormStatus::Copy](/api_help/form/classes/cformstatus/copy.php)

### Примеры использования

```
<?
$answer_id = 589; // ID ответа "да" на вопрос "Вы женаты/замужем?"
// скопируем ответ
if ($NEW_ANSWER_ID = CFormAnswer::Copy($answer_id))
{
	echo "Ответ #589 успешно скопирован в новый ответ #".$NEW_ANSWER_ID;
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