[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CForm](/api_help/form/classes/cform/index.php)

GetDropDownField (3.1.1)

GetDropDownField
================

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
string
CForm::GetDropDownField(
	string question_sid,
	array list,
	mixed value = "",
	string add_to_dropdown = "class=\"inputselect\""
)Копировать
```

Возвращает HTML код выпадающего списка одиночного выбора, предназначенного для выбора [ответа](/api_help/form/terms.php#answer) из группы ответов типа "dropdown" на вопрос, символьный идентификатор которого передается в параметре *question\_sid*.

Метод может использоваться как в форме
создания нового [результата](/api_help/form/terms.php#result), так и в форме редактирования существующего. Метод нестатический.

**Примечание**  
Имя результирующего HTML поля будет сформировано по следующей маске:  
 **form\_dropdown\_***question\_sid*

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| *question\_sid* | Символьный идентификатор [вопроса](/api_help/form/terms.php#question). |  |
| *list* | Массив ответов типа "dropdown" на вопрос *question\_sid*. Минимально требуемая структура данного массива:  ``` Array ( 	[reference] => Array 	( 		[0] => заголовок ответа 1 		[1] => заголовок ответа 2 		[2] => заголовок ответа 3 		... 	) 	[reference_id] => Array 	( 		[0] => ID ответа 1 		[1] => ID ответа 2 		[2] => ID ответа 3 		... 	) )Копировать ```  В данном массиве под *заголовком элемента* понимается параметр ANSWER\_TEXT [ответа](/api_help/form/terms.php#answer). |  |
| *value* | Если в данном параметре будет передано значение совпадающее с *ID ответа*, то данный ответ будет выбран в результирующем выпадающем списке:  `<option value="значение элемента" selected>заголовок ответа</option>`   Параметр необязательный. По умолчанию - "". |  |
| *add\_to\_dropdown* | Произвольный HTML который будет добавлен в результирующий HTML тег:  `<select add_to_dropdown ...>`   Параметр необязательный. По умолчанию - "class=\"inputselect\"". |  |

### Смотрите также

* [CForm::GetDropDownValue](/api_help/form/classes/cform/getdropdownvalue.php)
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
		<td>*Возраст:</td>
		<td><?
			// символьный идентификатор вопроса
			$QUESTION_SID = "AGE"; 
			// массив описывающий элементы выпадающего списка
			$arDropDown = array (
				"reference" => array (
					"-",
					"10-19",
					"20-29",
					"30-39",
					"40-49",
					"50-59",
					"60 и старше"
				),
				"reference_id" => array (
					608,
					596,
					597,
					598,
					599,
					600,
					601
				),
				"param" => array (
					"not_answer class=\"inputselect\"", // не является ответом
					"",
					"checked", // значение по умолчанию
					"",
					"",
					"",
					""
				)
			);
			// получим текущее значение выпадающего списка
			$value = CForm::GetDropDownValue($QUESTION_SID, $arDropDown, $arrVALUES);
			// выведем выпадающий список
			echo CForm::GetDropDownField(
				$QUESTION_SID,           // символьный идентификатор вопроса
				$arDropDown,             // массив описывающий элементы списка
				$value,                  // значение выбранного элемента списка
				"class=\"inputselect\""  // стиль выпадающего списка
			);            
		?></td>
	</tr>
</table>
<input type="submit" name="save" value="Сохранить">
</form>Копировать
```

Новинки документации в соцсетях: