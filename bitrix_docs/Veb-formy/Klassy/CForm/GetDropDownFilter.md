[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CForm](/api_help/form/classes/cform/index.php)

GetDropDownFilter (3.1.1)

GetDropDownFilter
=================

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
string
CForm::GetDropDownFilter(
	int field_id,
	string parameter_type,
	string filter_sid,
	string add_to_dropdown = "class=\"inputselect\""
)Копировать
```

Возвращает HTML код поля фильтра, представляющего из себя выпадающий список одиночного выбора. Данный выпадающий список может быть использован для фильтрации [результатов](/api_help/form/terms.php#result) по значению [ответа](/api_help/form/terms.php#answer) на [вопрос](/api_help/form/terms.php#question) [веб-формы](/api_help/form/terms.php#form). Значения этого выпадающего списка формируются из значений параметров [ответов](/api_help/form/terms.php#answer) - ANSWER\_TEXT или ANSWER\_VALUE. Метод нестатический.

**Примечание**  
Имя результирующего HTML поля будет сформировано по следующей маске:  
**find\_***filter\_sid*

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| *field\_id* | ID [вопроса](/api_help/form/terms.php#question)/[поля](/api_help/form/terms.php#field). |  |
| *parameter\_type* | Тип параметра [ответа](/api_help/form/terms.php#answer), допустимы следующие значения:  * **ANSWER\_TEXT**; * **ANSWER\_VALUE**. |  |
| *filter\_sid* | Идентификатор поля фильтра. Формируется по следующему шаблону:  *FSID***\_***QSID***\_***PTYPE***\_dropdown**,  где:  * *FSID* - символьный идентификатор [веб-формы](/api_help/form/terms.php#form); * *QSID* - символьный идентификатор [вопроса](/api_help/form/terms.php#question)/[поля](/api_help/form/terms.php#field) веб-формы; * *PTYPE* - тип параметра ответа, задаваемый в *parameter\_type.*  Примеры:  * ANKETA\_MARRIED\_ANSWER\_TEXT\_dropdown; * ANKETA\_CAR\_ANSWER\_VALUE\_dropdown. |  |
| *add\_to\_dropdown* | Произвольный HTML который будет добавлен в тег выпадающего списка:  `<select add_to_dropdown ...>`   Параметр необязательный. По умолчанию - "class=\"inputselect\"". |  |

### Смотрите также

* [CForm::GetTextFilter](/api_help/form/classes/cform/gettextfilter.php)
* [CForm::GetDateFilter](/api_help/form/classes/cform/getdatefilter.php)
* [CForm::GetNumberFilter](/api_help/form/classes/cform/getnumberfilter.php)
* [CForm::GetExistFlagFilter](/api_help/form/classes/cform/getexistflagfilter.php)

### Примеры использования

```
<form name="form1" action="" method="POST">
<table>
	<tr>
		<td>Образование:</td>
		<td><?
			$FIELD_ID = 15; // ID вопроса "Ваше образование?"
			echo CForm::GetDropDownFilter(
				$FIELD_ID, 
				"ANSWER_TEXT", 
				"ANKETA_EDUCATION_ANSWER_TEXT_dropdown", 
				"class=\"inputselect\""
			);
		?></td>
	</tr>
</table>
<input type="submit" value="Фильтр">
</form>Копировать
```

Новинки документации в соцсетях: