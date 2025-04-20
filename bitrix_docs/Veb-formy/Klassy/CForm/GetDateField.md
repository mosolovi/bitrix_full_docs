[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CForm](/api_help/form/classes/cform/index.php)

GetDateField (3.1.1)

GetDateField
============

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
string
CForm::GetDateField(
	int answer_id,
	string html_form_name,
	string value = "",
	mixed size = "",
	string add_to_text = "class=\"inputtext\""
)Копировать
```

Возвращает HTML код однострочного текстового поля. Данное поле предназначено для ввода [ответа](/api_help/form/terms.php#answer) типа "date". В результирующий HTML код будет добавлена иконка, ведущая на страницу с календарем.

Метод может использоваться как в форме
создания нового [результата](/api_help/form/terms.php#result), так и в форме редактирования существующего. Метод нестатический.

**Примечание**  
Имя результирующего HTML поля для ввода даты будет сформировано по следующей маске:  
 **form\_date\_***answer\_id*

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| *answer\_id* | ID [ответа](/api_help/form/terms.php#answer). |  |
| *html\_form\_name* | Имя HTML формы для создания нового [результата](/api_help/form/terms.php#result) или редактирования существующего.  `<form name="html_form_name" ...>`   Параметр необязательный. По умолчанию - "form1". |  |
| *value* | Значение результирующего текстового поля:  `<input type="text" value="value" ...>` Параметр необязательный. По умолчанию - "". |  |
| *size* | Ширина результирующего текстового поля для ввода даты:  `<input type="text" size="size" ...>` Параметр необязательный. По умолчанию - "". |  |
| *add\_to\_text* | Произвольный HTML который будет добавлен в результирующий HTML тег текстового поля для ввода даты:  `<input type="text" add_to_text ...>` Параметр необязательный. По умолчанию - "class=\"inputtext\"". |  |

### Смотрите также

* [CForm::GetDateValue](/api_help/form/classes/cform/getdatevalue.php)
* [Имена HTML полей](/api_help/form/htmlnames.php)

### Примеры использования

```
<?
/*******************************************
       Редактирование результата
*******************************************/
$RESULT_ID = 12; // ID результата
// если была нажата кнопка "Сохранить" то
if (strlen($_REQUEST["save"])>0)
{
	// используем данные пришедшие с формы
	$arrVALUES = $_REQUEST; 
}
else
{
	// сформируем этот массив из данных по результату
	$arrVALUES = CFormResult::GetDataByIDForHTML($RESULT_ID); 
}
?>
<form name="ANKETA" action="" method="POST">
<table>
	<tr>
		<td>Дата рождения:</td>
		<td><?
			// массив описывающий поле для ввода даты
			// содержит минимально-необходимые поля
			$arAnswer = array(
				"ID"            => 587,   // ID поля для ответа на вопрос "Дата рождения?"
				"VALUE"         => "",    // параметр ANSWER_VALUE (значение по умолчанию)
				"FIELD_WIDTH"   => 10,    // ширина поля
				"FIELD_PARAM"   => ""     // параметры поля
			);
            
			// получим текущее значение
			$value = CForm::GetDateValue($arAnswer["ID"], $arAnswer, $arrVALUES);
			// выведем поле
			echo CForm::GetDateField(
				$arAnswer["ID"],
				"ANKETA",
				$value,
				$arAnswer["FIELD_WIDTH"],
				$arAnswer["FIELD_PARAM"]
			);
		?></td>
	</tr>
</table>
<input type="submit" name="save" value="Сохранить">
</form>Копировать
```

Новинки документации в соцсетях: