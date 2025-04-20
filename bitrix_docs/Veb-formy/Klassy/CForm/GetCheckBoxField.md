[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CForm](/api_help/form/classes/cform/index.php)

GetCheckBoxField (3.1.1)

GetCheckBoxField
================

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
string
CForm::GetCheckBoxField(
	string question_sid,
	int answer_id,
	mixed value = "",
	string add_to_checkbox = "class=\"inputcheckbox\""
)Копировать
```

Возвращает HTML код флага множественного выбора (checkbox), предназначенного для выбора [ответа](/api_help/form/terms.php#answer) типа "checkbox" на вопрос, символьный идентификатор которого передается в параметре *question\_sid*. Метод нестатический.

Метод может использоваться как в форме создания нового [результата](/api_help/form/terms.php#result), так и в форме редактирования существующего.

**Примечание**  
Имя результирующего HTML поля будет сформировано по следующей маске:  
 **form\_checkbox\_***question\_sid***[]**

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *question\_sid* | Символьный идентификатор [вопроса](/api_help/form/terms.php#question). |
| *answer\_id* | ID [ответа](/api_help/form/terms.php#answer). |
| *value* | Если в данном параметре будет передано значение, совпадающее с *answer\_id*, то флаг множественного выбора будет отмечен (*checked*):  `<input type="checkbox" checked ...>`   Параметр необязательный. По умолчанию - "". |
| *add\_to\_checkbox* | Произвольный HTML, который будет добавлен в результирующий HTML тег флага множественного выбора:  <input type="checkbox" *add\_to\_checkbox* ...>    Необходимо учитывать, что если в данном параметре задать ключевое слово "checked", то данный переключатель будет выбран по умолчанию.   Параметр необязательный. По умолчанию - "class=\"inputcheckbox\"". |

### Смотрите также

* [CForm::GetCheckBoxValue](/api_help/form/classes/cform/getcheckboxvalue.php)
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
	// используем данные, пришедшие с формы
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
		<td>Какие области знаний вас интересуют ?</td>
		<td><?
            
			/**********************************************************
				выводим два checkbox'а (математика/физика) 
				как варианты ответа на вопрос 
				"Какие области знаний вас интересуют ?"
			**********************************************************/
			$QUESTION_SID = "INTEREST"; // символьный идентификатор вопроса
			/***********************
			checkbox "математика"
			***********************/
			// массив описывающий один checkbox
			// содержит минимально-необходимые поля
			$arAnswer = array(
				"ID"            => 591,            // ID checkbox'а
				"FIELD_PARAM"   => "checked class=\"inputcheckbox\""   // параметр ответа
			);
			// получим текущее значение
			$value = CForm::GetCheckBoxValue($QUESTION_SID, $arAnswer, $arrVALUES);
			// выведем checkbox
			echo CForm::GetCheckBoxField(
				$QUESTION_SID,
				$arAnswer["ID"],
				$value,
				$arAnswer["FIELD_PARAM"]
			);            
			echo "математика<br>";
			/***********************
				checkbox "физика"
			***********************/
			// массив описывающий один checkbox
			// содержит минимально-необходимые поля
			$arAnswer = array(
				"ID"            => 593,       // ID checkbox'а
				"FIELD_PARAM"   => ""         // параметр ответа
			);
			// получим текущее значение
			$value = CForm::GetCheckBoxValue($QUESTION_SID, $arAnswer, $arrVALUES);
			// выведем checkbox
			echo CForm::GetCheckBoxField(
				$QUESTION_SID,
				$arAnswer["ID"],
				$value,
				$arAnswer["FIELD_PARAM"]
			);            
			echo "физика";
		?></td>
	</tr>
</table>
<input type="submit" name="save" value="Сохранить">
</form>Копировать
```

Новинки документации в соцсетях: