[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CForm](/api_help/form/classes/cform/index.php)

GetNumberFilter (3.1.1)

GetNumberFilter
===============

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
string
CForm::GetNumberFilter(
	int filter_sid,
	int size = "10",
	string add_to_text = "class=\"inputtext\""
)Копировать
```

Возвращает HTML код поля фильтра, предназначенного для фильтрации [результатов](/api_help/form/terms.php#result) по цифровым значениям, введенным в качестве ответа на [вопрос](/api_help/form/terms.php#question) веб-формы, либо цифровым значениям [полей](/api_help/form/terms.php#field) веб-формы. Возвращаемый HTML код включает в себя два поля, предназначенных для ввода числового интервала. Метод нестатический.

**Примечание**  
Имена результирующих HTML полей будут сформированы по следующим маскам:  
**find\_***filter\_sid***\_1** - первое поля числового интервала (с)
  
**find\_***filter\_sid***\_2** - второе поле числового интервала (по)

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| *filter\_sid* | Идентификатор поля фильтра. Формируется по следующему шаблону:  *FSID***\_***QSID***\_***PTYPE***\_integer**,  где:  * *FSID* - символьный идентификатор [веб-формы](/api_help/form/terms.php#form), * *QSID* - символьный идентификатор [вопроса](/api_help/form/terms.php#question)/[поля](/api_help/form/terms.php#field) веб-формы; * *PTYPE* - тип параметра, по которому будет фильтрация, возможны следующие значения:   + *ANSWER\_TEXT* - параметр ANSWER\_TEXT [вопроса](/api_help/form/terms.php#question) веб-формы;   + *ANSWER\_VALUE* - параметр ANSWER\_VALUE [вопроса](/api_help/form/terms.php#question) веб-формы;   + *USER* - для [вопроса](/api_help/form/terms.php#question) веб-формы - вводимое с клавиатуры значение, для [полей](/api_help/form/terms.php#field) веб-формы - значение этого поля веб-формы.  Примеры:  * ANKETA\_AGE\_USER\_integer; * ANKETA\_CAR\_POWER\_ANSWER\_VALUE\_integer. |  |
| *size* | Ширина однострочного текстового поля:  `<input type="text" size="size" ...>`   Параметр необязательный. По умолчанию - "10". |  |
| *add\_to\_text* | Произвольный HTML, который будет добавлен в теги однострочных текстовых полей, в которых вводится дата:  `<input type="text" add_to_text ...>`   Параметр необязательный. По умолчанию - "class=\"inputtext\"". |  |

### Смотрите также

* [CalendarPeriod](/api_help/main/functions/date/calendarperiod.php)
* [CForm::GetTextFilter](/api_help/form/classes/cform/gettextfilter.php)
* [CForm::GetDropDownFilter](/api_help/form/classes/cform/getdropdownfilter.php)
* [CForm::GetDateFilter](/api_help/form/classes/cform/getdatefilter.php)
* [CForm::GetExistFlagFilter](/api_help/form/classes/cform/getexistflagfilter.php)

### Примеры использования

```
<form name="form1" action="" method="POST">
<table>
	<tr>
		<td>Возраст:</td>
		<td><?
			echo CForm::GetNumberFilter(
				"ANKETA_AGE_USER_integer", 
				"10", 
				"class=\"inputtext\""
			);
		?></td>
	</tr>
</table>
<input type="submit" value="Фильтр">
</form>Копировать
```

Новинки документации в соцсетях: