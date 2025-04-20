[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CForm](/api_help/form/classes/cform/index.php)

GetExistFlagFilter (4.0.4)

GetExistFlagFilter
==================

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
string
CForm::GetExistFlagFilter(
	int filter_sid,
	string add_to_checkbox = "class=\"inputcheckbox\""
)Копировать
```

Возвращает HTML код поля фильтра, предназначенного для фильтрации [результатов](/api_help/form/terms.php#result) по факту существования значения [ответа](/api_help/form/terms.php#answer) на [вопрос веб-формы](/api_help/form/terms.php#question) или факту существования значения [поля](/api_help/form/terms.php#field) веб-формы. Возвращаемый HTML код включает в себя флаг множественного выбора
(**checkbox**). Метод нестатический.

**Примечание**  
Имя результирующего HTML поля будет сформировано по следующей маске:  
**find\_***filter\_sid*

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *filter\_sid* | Идентификатор поля фильтра. Формируется по следующему шаблону:  *FSID***\_***QSID***\_***PTYPE***\_exist**,  где:  * *FSID* - символьный идентификатор [веб-формы](/api_help/form/terms.php#form); * *QSID* - символьный идентификатор [вопроса](/api_help/form/terms.php#question)/[поля](/api_help/form/terms.php#field) веб-формы; * *PTYPE* - тип параметра по которому будет фильтрация, возможны следующие значения:   + *ANSWER\_TEXT* - параметр ANSWER\_TEXT [вопроса](/api_help/form/terms.php#question) веб-формы;   + *ANSWER\_VALUE* - параметр ANSWER\_VALUE [вопроса](/api_help/form/terms.php#question) веб-формы;   + *USER* - для [вопроса](/api_help/form/terms.php#question) веб-формы - вводимое с клавиатуры значение, для [полей](/api_help/form/terms.php#field) веб-формы - значение этого поля веб-формы.  Примеры:  * ANKETA\_USER\_NAME\_USER\_text; * ANKETA\_TEST\_FIELD\_USER\_text. |
| *add\_to\_checkbox* | Произвольный HTML который будет добавлен в тег флага выпадающего списка:  `<input type="checkbox" add_to_checkbox ...>`   Параметр необязательный. По умолчанию - "class=\"inputcheckbox\"". |

### Смотрите также

* [CForm::GetDateFilter](/api_help/form/classes/cform/getdatefilter.php)
* [CForm::GetDropDownFilter](/api_help/form/classes/cform/getdropdownfilter.php)
* [CForm::GetNumberFilter](/api_help/form/classes/cform/getnumberfilter.php)
* [CForm::GetTextFilter](/api_help/form/classes/cform/gettextfilter.php)

### Примеры использования

```
<form action="" method="POST">
<table>
	<tr>
		<td>Есть фотография?</td>
		<td><?
			echo CForm::GetExistFlagFilter(
				"ANKETA_PHOTO_USER_exist", 
				"class=\"inputcheckbox\""
			);
		?></td>
	</tr>
</table>
<input type="submit" value="Фильтр">
</form>Копировать
```

Новинки документации в соцсетях: