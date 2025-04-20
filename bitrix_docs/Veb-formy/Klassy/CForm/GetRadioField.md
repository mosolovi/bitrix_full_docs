[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CForm](/api_help/form/classes/cform/index.php)

GetRadioField (3.1.1)

GetRadioField
=============

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
string
CForm::GetRadioField(
	string question_sid,
	int answer_id,
	mixed value = "",
	string add_to_radio = "class=\"inputradio\""
)Копировать
```

Возвращает HTML код переключателя одиночного выбора (radio-кнопка), предназначенного для выбора [ответа](/api_help/form/terms.php#answer) типа "radio" на вопрос, символьный идентификатор которого передается в параметре *question\_sid*.

Метод может использоваться как в форме содания нового [результата](/api_help/form/terms.php#result), так и в форме редактирования существующего. Метод нестатический.

Имя результирующего HTML поля будет сформировано по следующей маске: **form\_radio\_***question\_sid*

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *question\_sid* | Символьный идентификатор [вопроса](/api_help/form/terms.php#question). |
| *answer\_id* | ID [ответа](/api_help/form/terms.php#answer). |
| *value* | Если в данном параметре будет передано значение совпадающее с *answer\_id*, то переключатель одиночного выбора будет выбран (checked):  <input type="radio" checked ...>  Параметр необязательный. По умолчанию - "". |
| *add\_to\_radio* | Произвольный HTML который будет добавлен в результирующий HTML тег переключателя одиночного выбора:  <input type="radio" *add\_to\_radio* ...>  Необходимо учитывать что если в данном параметре задать ключевое слово "checked", то данный переключатель будет выбран по умолчанию.  Параметр необязательный. По умолчанию - "class=\"inputradio\"". |

### Смотрите также

* [CForm::GetRadioValue](/api_help/form/classes/cform/getradiovalue.php)
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
		<td>Вы курите?</td>
		<td><?
            
			/**********************************************************
				выводим две radio-кнопки (да/нет) 
				как варианты ответа на вопрос "Вы курите?"
			**********************************************************/
			$QUESTION_SID = "SMOKE"; // символьный идентификатор вопроса
			/***********************
				radio-кнопка "да"
			***********************/
			// массив описывающий одну radio-кнопку
			// содержит минимально-необходимые поля
			$arAnswer = array(
				"ID"            => 589,    // ID radio-кнопки
				"FIELD_PARAM"   => "checked class=\"inputradio\""   // параметр ответа
			);
            
			// получим текущее значение
			$value = CForm::GetRadioValue($QUESTION_SID, $arAnswer, $arrVALUES);
			// выведем radio-кнопку
			echo CForm::GetRadioField(
				$QUESTION_SID,
				$arAnswer["ID"],
				$value,
				$arAnswer["FIELD_PARAM"]
			);            
			echo "да <br>";
			/***********************
				radio-кнопка "нет"
			***********************/
			// массив описывающий одну radio-кнопку
			// содержит минимально-необходимые поля
			$arAnswer = array(
				"ID"            => 590,    // ID radio-кнопки
				"FIELD_PARAM"   => ""      // параметр ответа
			);
            
			// получим текущее значение
			$value = CForm::GetRadioValue($QUESTION_SID, $arAnswer, $arrVALUES);
			// выведем radio-кнопку
			echo CForm::GetRadioField(
				$QUESTION_SID,
				$arAnswer["ID"],
				$value,
				$arAnswer["FIELD_PARAM"]
			);            
			echo "нет";
		?></td>
	</tr>
</table>
<input type="submit" name="save" value="Сохранить">
</form>Копировать
```

Новинки документации в соцсетях: