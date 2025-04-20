[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CForm](/api_help/form/classes/cform/index.php)

GetTextField (3.1.1)

GetTextField
============

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
string
CForm::GetTextField(
	int answer_id,
	string value = "",
	mixed size = "",
	string add_to_text = "class=\"inputtext\""
)Копировать
```

Возвращает HTML код однострочного текстового поля. Данное поле предназначено для ввода [ответа](/api_help/form/terms.php#answer) типа "text".

Метод может использоваться как в форме
создания нового [результата](/api_help/form/terms.php#result), так и в форме редактирования существующего. Метод нестатический.

**Примечание**  
Имя результирующего HTML поля будет сформировано по следующей маске:  
 **form\_text\_***answer\_id*

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *answer\_id* | ID [ответа](/api_help/form/terms.php#answer). |
| *value* | Значение результирующего текстового поля:  `<input type="text" value="value" ...>`   Параметр необязательный. По умолчанию - "". |
| *size* | Ширина результирующего текстового поля:  `<input type="text" size="size" ...>`   Параметр необязательный. По умолчанию - "". |
| *add\_to\_text* | Произвольный HTML, который будет добавлен в результирующий HTML тег текстового поля:  `<input type="text" add_to_text ...>`   Параметр необязательный. По умолчанию - "class=\"inputtext\"". |

### Смотрите также

* [CForm::GetTextValue](/api_help/form/classes/cform/gettextvalue.php)
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
		<td>Фамилия:</td>
		<td><?
			// массив описывающий однострочное текстовое поле
			// содержит минимально-необходимые поля
			$arAnswer = array(
				"ID"            => 586,   // ID поля для ответа на вопрос "Ваша фамилия?"
				"VALUE"         => "",    // параметр ANSWER_VALUE (значение по умолчанию)
				"FIELD_WIDTH"   => 10,    // ширина поля
				"FIELD_PARAM"   => ""     // параметры поля
			);
			// получим текущее значение
			$value = CForm::GetTextValue($arAnswer["ID"], $arAnswer, $arrVALUES);
			// выведем поле
			echo CForm::GetTextField(
				$arAnswer["ID"],
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