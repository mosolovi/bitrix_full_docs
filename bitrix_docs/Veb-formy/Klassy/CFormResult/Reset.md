[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormResult](/api_help/form/classes/cformresult/index.php)

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
CFormResult::Reset(
	int result_id,
	bool del_files = true,
	string del_fields = "N",
	array exception = array()
)Копировать
```

Удаляет все значения [ответов](/api_help/form/terms.php#answer) на [вопросы](/api_help/form/terms.php#question) веб-формы, а также значения [полей](/api_help/form/terms.php#field) веб-формы для указанного [результата](/api_help/form/terms.php#result). Сам результат при этом остается. Если в процессе работы метода ошибок не возникло, то метод возвращает "true". Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *result\_id* | ID [результата](/api_help/form/terms.php#result). |
| *del\_files* | Флаг необходимости удаления файлов, загруженных в качестве значения [ответа](/api_help/form/terms.php#answer) на [вопрос](/api_help/form/terms.php#question).  Параметр необязательный. По умолчанию - "true" (файлы необходимо удалить). |
| *del\_fields* | Флаг необходимости удаления значений [полей](/api_help/form/terms.php#field) веб-формы.  Параметр необязательный. По умолчанию - "N" (значения [полей](/api_help/form/terms.php#field) необходимо удалить). |
| *exception* | Массив ID [вопросов](/api_help/form/terms.php#question) и [полей](/api_help/form/terms.php#field) веб-формы, для которых не нужно удалять значения.  Параметр необязательный. По умолчанию - пустой массив. |

### Смотрите также

* [CForm::Reset](/api_help/form/classes/cform/reset.php);
* [CFormField::Reset](/api_help/form/classes/cformfield/reset.php)

### Примеры использования

```
<?
$RESULT_ID = 189; // ID результата
// удалим все значения ответов на вопросы и полей веб-формы
// вместе с файлами
// исключение составят вопросы с ID = 140 и ID = 141
CFormResult::Reset($RESULT_ID, true, "Y", array(140, 141));
?>Копировать
```

Новинки документации в соцсетях: