[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CForm](/api_help/form/classes/cform/index.php)

GetDateFilter (3.1.1)

GetDateFilter
=============

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
string
CForm::GetDateFilter(
	int filter_sid,
	string html_form_name = "form1",
	string show_dropdown = "Y",
	string add_to_dropdown = "class=\"inputselect\"",
	string add_to_text = "class=\"inputtext\""
)Копировать
```

Возвращает HTML код поля фильтра, предназначенного для фильтрации [результатов](/api_help/form/terms.php#result) по датам, введенным в качестве ответа на [вопрос](/api_help/form/terms.php#question) веб-формы, либо значений [полей](/api_help/form/terms.php#field) веб-формы типа "дата". Возвращаемый HTML код включает в себя два поля, предназначенных для ввода интервала дат, а также некоторые вспомогательные элементы (календарь, выпадающий список дней). Метод нестатический.

**Примечание**  
Имена результирующих HTML полей будут сформированы по следующим маскам:  
**find\_***filter\_sid***\_1** - первое поля интервала дат (с)
  
**find\_***filter\_sid***\_2** - второе поле интервала дат (по)

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| *filter\_sid* | Идентификатор поля фильтра. Формируется по следующему шаблону:  *FSID***\_***QSID***\_USER\_date**,  где:  * *FSID* - символьный идентификатор [веб-формы](/api_help/form/terms.php#form); * *QSID* - символьный идентификатор [вопроса](/api_help/form/terms.php#question)/[поля](/api_help/form/terms.php#field) веб-формы.  Примеры:  * ANKETA\_USER\_BIRTHDAY\_USER\_date * ANKETA\_DATE\_FIELD\_USER\_date |  |
| *html\_form\_name* | Имя HTML формы, в которой выводится фильтр.  `<form name="html_form_name" ...>`   Параметр необязательный. По умолчанию - "form1". |  |
| *show\_dropdown* | Если значение "Y", то возвращаемый HTML код будет включать выпадающий список дней, предназначенный для облегчения выбора даты.   Параметр необязательный. По умолчанию - "Y" (вывести выпадающий список дней). |  |
| *add\_to\_dropdown* | Если *show\_dropdown*="Y", то в данном параметре можно указать произвольный HTML, который будет добавлен в тег выпадающего списка дней:  `<select add_to_dropdown ...>`   Параметр необязательный. По умолчанию - "class=\"inputselect\"". |  |
| *add\_to\_text* | Произвольный HTML, который будет добавлен в теги однострочных текстовых полей, предназначенных для ввода даты:  `<input type="text" add_to_text ...>`   Параметр необязательный. По умолчанию - "class=\"inputtext\"". |  |
| *field\_select* | Необязательный параметр. | 3.3.0 |
| *field\_input* | Необязательный параметр. Изменен с 4.0.4 | 3.3.0 |

### Смотрите также

* [CalendarPeriod](/api_help/main/functions/date/calendarperiod.php)
* [CForm::GetTextFilter](/api_help/form/classes/cform/gettextfilter.php)
* [CForm::GetDropDownFilter](/api_help/form/classes/cform/getdropdownfilter.php)
* [CForm::GetNumberFilter](/api_help/form/classes/cform/getnumberfilter.php)
* [CForm::GetExistFlagFilter](/api_help/form/classes/cform/getexistflagfilter.php)

### Примеры использования

```
<form name="form1" action="" method="POST">
<table>
	<tr>
		<td>Дата рождения:</td>
		<td><?
			echo CForm::GetDateFilter(
				"ANKETA_USER_BIRTHDAY_USER_date", 
				"form1", 
				"Y", 
				"class=\"inputselect\"", 
				"class=\"inputtext\""
			);
		?></td>
	</tr>
</table>
<input type="submit" value="Фильтр">
</form>Копировать
```

Новинки документации в соцсетях: