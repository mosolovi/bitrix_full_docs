[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CForm](/api_help/form/classes/cform/index.php)

GetDateValue (3.1.1)

GetDateValue
============

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
string
CForm::GetDateValue(
	int answer_id,
	array answer,
	mixed form_values = false
)Копировать
```

Если массив, переданный в параметре *form\_values,* инициализирован (например, в момент редактирования [результата](/api_help/form/terms.php#result)), то метод возвращает текущее значение [ответа](/api_help/form/terms.php#answer) типа "date", ID которого передается в параметре *answer\_id*.

Если массив, переданный в параметре *form\_values,* не инициализирован (например, в момент создания нового [результата](/api_help/form/terms.php#result)), то метод вернет значение по умолчанию для данного [ответа](/api_help/form/terms.php#answer) (т.е. то что задается в *answer*["VALUE"]).

Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *answer\_id* | ID [ответа](/api_help/form/terms.php#answer). |
| *answer* | Массив, описывающий параметры [ответа](/api_help/form/terms.php#answer), обязательным элементом которого является элемент с ключом **VALUE** и значением, в котором содержится значение по умолчанию для [ответа](/api_help/form/terms.php#answer). Как правило, таким значением по умолчанию становится параметр ANSWER\_VALUE [ответа](/api_help/form/terms.php#answer). |
| *form\_values* | Ассоциированный массив значений, пришедших с веб-формы при создании нового или редактировании существующего [результата](/api_help/form/terms.php#result) (стандартный массив **$\_REQUEST**). Данный массив может быть также получен с помощью метода [CFormResult::GetDataByIDForHTML](/api_help/form/classes/cformresult/getdatabyidforhtml.php).   Параметр необязательный. По умолчанию - "false". |

### Смотрите также

* [CForm::GetDateField](/api_help/form/classes/cform/getdatefield.php)

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