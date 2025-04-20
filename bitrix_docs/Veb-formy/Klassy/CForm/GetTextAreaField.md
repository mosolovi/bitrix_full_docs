[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CForm](/api_help/form/classes/cform/index.php)

GetTextAreaField (3.1.1)

GetTextAreaField
================

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
string
CForm::GetTextAreaField(
	int answer_id,
	int cols = "",
	int rows = "",
	string add_to_textarea = "class=\"inputtextarea\""
	string value = "",
)Копировать
```

Возвращает HTML код многострочного текстового поля. Данное поле предназначено для ввода [ответа](/api_help/form/terms.php#answer) типа "textarea".

Метод может использоваться как в форме
создания нового [результата](/api_help/form/terms.php#result), так и в форме редактирования существующего. Метод нестатический.

**Примечание**  
Имя результирующего HTML поля будет сформировано по следующей маске:  
 **form\_textarea\_***answer\_id*

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *answer\_id* | ID [ответа](/api_help/form/terms.php#answer). |
| *cols* | Ширина результирующего многострочного текстового поля:  `<textarea cols="cols" ...>`   Параметр необязательный. По умолчанию - "". |
| *rows* | Высота результирующего многострочного текстового поля:  `<textarea rows="rows" ...>`   Параметр необязательный. По умолчанию - "". |
| *add\_to\_textarea* | Произвольный HTML, который будет добавлен в результирующий тег многострочного текстового поля:  `<textarea add_to_textarea ...>`   Параметр необязательный. По умолчанию - "class=\"inputtextarea\"". |
| *value* | Значение результирующего многострочного текстового поля:  `<textarea ...>value</textarea>`   Параметр необязательный. По умолчанию - "". |

### Смотрите также

* [CForm::GetTextAreaValue](/api_help/form/classes/cform/gettextareavalue.php)
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
<form action="" method="POST">
<table>
	<tr>
		<td>Адрес:</td>
		<td><?
			// массив описыващий многострочное текстовое поле
			// содержит минимально-необходимые поля
			$arAnswer = array(
				"ID"            => 588,   // ID поля для ответа на вопрос "Ваш адрес?"
				"VALUE"         => "",    // параметр ANSWER_VALUE (значение по умолчанию)
				"FIELD_WIDTH"   => 10,    // ширина поля
				"FIELD_HEIGHT"  => 5,     // высота поля
				"FIELD_PARAM"   => ""     // параметры поля
			);
			// получим текущее значение
			$value = CForm::GetTextAreaValue($arAnswer["ID"], $arAnswer, $arrVALUES);
			// выведем поле
			echo CForm::GetTextAreaField(
				$arAnswer["ID"], 
				$arAnswer["FIELD_WIDTH"], 
				$arAnswer["FIELD_HEIGHT"], 
				$arAnswer["FIELD_PARAM"],
				$value
			);
		?></td>
	</tr>
</table>
<input type="submit" name="save" value="Сохранить">
</form>Копировать
```

Новинки документации в соцсетях: