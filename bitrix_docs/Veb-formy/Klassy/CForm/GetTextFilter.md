[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CForm](/api_help/form/classes/cform/index.php)

GetTextFilter (3.1.1)

GetTextFilter
=============

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
string
CForm::GetTextFilter(
	int filter_sid,
	int size = 45,
	string add_to_text = "class=\"inputtext\"",
	string add_to_checkbox = "class=\"inputcheckbox\""
)Копировать
```

Возвращает HTML код поля фильтра, предназначенного для фильтрации [результатов](/api_help/form/terms.php#result) по текстовым значениям [ответов](/api_help/form/terms.php#answer) на [вопросы веб-формы](/api_help/form/terms.php#question) или текстовым значениям [полей](/api_help/form/terms.php#field) веб-формы. Возвращаемый HTML код включает в себя однострочное текстовое поле и флаг для установки точности фильтрации. Метод нестатический.

**Примечание**  
Имена результирующих HTML полей будут сформированы по следующим маскам:  
**find\_***filter\_sid* - однострочное текстовое поля  
**find\_***filter\_sid***\_exact\_match** - флаг для установки точности фильтрации

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| *filter\_sid* | Идентификатор поля фильтра. Формируется по следующему шаблону:  *FSID***\_***QSID***\_***PTYPE***\_text**,  где:  * *FSID* - символьный идентификатор [веб-формы](/api_help/form/terms.php#form); * *QSID* - символьный идентификатор [вопроса](/api_help/form/terms.php#question)/[поля](/api_help/form/terms.php#field) веб-формы; * *PTYPE* - тип параметра по которому будет фильтрация, возможны следующие значения:   + *ANSWER\_TEXT* - параметр ANSWER\_TEXT [вопроса](/api_help/form/terms.php#question) веб-формы;   + *ANSWER\_VALUE* - параметр ANSWER\_VALUE [вопроса](/api_help/form/terms.php#question) веб-формы;   + *USER* - для [вопроса](/api_help/form/terms.php#question) веб-формы - вводимое с клавиатуры значение, для [полей](/api_help/form/terms.php#field) веб-формы - значение этого поля веб-формы.  Примеры:  * ANKETA\_USER\_NAME\_USER\_text; * ANKETA\_TEST\_FIELD\_USER\_text. |  |
| *size* | Ширина однострочного текстового поля:  `<input type="text" size="size" ...>`   Параметр необязательный. По умолчанию - "45". |  |
| *add\_to\_text* | Произвольный HTML, который будет добавлен в тег однострочного текстового поля:  `<input type="text" add_to_text ...>`   Параметр необязательный. По умолчанию - "class='typeinput'". С версии 4.0.4 - "class=\"inputtext\"" | 3.2.5 |
| *add\_to\_checkbox* | Произвольный HTML, который будет добавлен в тег флага для установки точности фильтрации:  `<input type="checkbox" add_to_checkbox ...>`   Параметр необязательный. По умолчанию - "class=\"inputcheckbox\"". | 3.3.10 |

### Смотрите также

* [CForm::GetDateFilter](/api_help/form/classes/cform/getdatefilter.php)
* [CForm::GetDropDownFilter](/api_help/form/classes/cform/getdropdownfilter.php)
* [CForm::GetNumberFilter](/api_help/form/classes/cform/getnumberfilter.php)
* [CForm::GetExistFlagFilter](/api_help/form/classes/cform/getexistflagfilter.php)

### Примеры использования

```
<form action="" method="POST">
<table>
	<tr>
		<td>Фамилия:</td>
		<td><?
			echo CForm::GetTextFilter(
				"ANKETA_USER_NAME_USER_text", 
				45, 
				"class=\"inputtext\"", 
				"class=\"inputcheckbox\""
			);
		?></td>
	</tr>
</table>
<input type="submit" value="Фильтр">
</form>Копировать
```

Новинки документации в соцсетях: