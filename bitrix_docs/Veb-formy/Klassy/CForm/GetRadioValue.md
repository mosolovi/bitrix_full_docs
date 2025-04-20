[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CForm](/api_help/form/classes/cform/index.php)

GetRadioValue (3.1.1)

GetRadioValue
=============

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
int
CForm::GetRadioValue(
	string question_sid,
	array answer,
	mixed form_values = false
)Копировать
```

Если массив, переданный в параметре *form\_values,* инициализирован (например, в момент редактирования [результата](/api_help/form/terms.php#result)), то метод возвращает ID [ответа](/api_help/form/terms.php#answer), выбранного среди группы ответов типа "radio" на вопрос, символьный идентификатор которого указан в параметре *question\_sid*.

Если массив, переданный в параметре *form\_values,* не инициализирован (например, в момент создания нового [результата](/api_help/form/terms.php#result)), то метод вернет ID [ответа](/api_help/form/terms.php#answer) (*answer*["ID"]), если он был установлен как ответ по умолчанию (ответами по умолчанию считаются те, у которых присутствует строка "checked" в *answer*["FIELD\_PARAM"]).

Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *question\_sid* | Символьный идентификатор [вопроса](/api_help/form/terms.php#question). |
| *answer* | Массив описывающий параметры [ответа](/api_help/form/terms.php#answer), с обязательными ключами:  * **ID** - ID [ответа](/api_help/form/terms.php#answer); * **FIELD\_PARAM** - если значение этого ключа содержит слово "checked", то ID этого ответа будет возвращен данным методом по умолчанию (т.е. при создании нового [результата](/api_help/form/terms.php#result)). |
| *form\_values* | Ассоциированный массив значений, пришедших с веб-формы при создании нового или редактировании существующего [результата](/api_help/form/terms.php#result) (стандартный массив **$\_REQUEST**). Данный массив может быть также получен с помощью метода [CFormResult::GetDataByIDForHTML](/api_help/form/classes/cformresult/getdatabyidforhtml.php).   Параметр необязательный. По умолчанию - "false". |

### Смотрите также

* [CForm::GetRadioField](/api_help/form/classes/cform/getradiofield.php)

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