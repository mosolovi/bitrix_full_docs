[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CForm](/api_help/form/classes/cform/index.php)

GetMultiSelectValue (3.1.1)

GetMultiSelectValue
===================

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
array
CForm::GetMultiSelectValue(
	string question_sid,
	array answer_list,
	mixed form_values = false
)Копировать
```

Если массив, переданный в параметре *form\_values,* инициализирован (например, в момент редактирования [результата](/api_help/form/terms.php#result)), то метод возвращает массив ID [ответов](/api_help/form/terms.php#answer), выбранных среди группы ответов типа
"**multiselect**" на вопрос, символьный идентификатор которого указан в параметре *question\_sid*.

Если массив, переданный в параметре *form\_values,* не инициализирован (например, в момент создания нового [результата](/api_help/form/terms.php#result)), то метод вернет массив ID [ответов](/api_help/form/terms.php#answer), выбранных по умолчанию. Поиск ответа по умолчанию осуществляется среди группы ответов, задаваемых в параметре *answer\_list,* посредством поиска строки "checked" в *answer\_list*["param"][i]; если такая строка будет найдена, то метод добавит данный ID [ответа](/api_help/form/terms.php#answer) (хранимый в *answer\_list*["reference\_id"][i]) в результирующий массив.

Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *question\_sid* | Символьный идентификатор [вопроса](/api_help/form/terms.php#question). |
| *answer\_list* | Массив ответов типа "multiselect" на вопрос *question\_sid*. Минимально требуемая структура данного массива:  ``` Array ( 	[reference_id] => Array 	( 		[0] => ID ответа 1 		[1] => ID ответа 2 		[2] => ID ответа 3 		... 	) 	[param] => Array 	( 		[0] => параметр ответа 1 		[1] => параметр ответа 2 		[2] => параметр ответа 3 		... 	) )Копировать ``` |
| *form\_values* | Ассоциированный массив значений, пришедших с веб-формы при создании нового или редактировании существующего [результата](/api_help/form/terms.php#result) (стандартный массив **$\_REQUEST**). Данный массив может быть также получен с помощью функции [CFormResult::GetDataByIDForHTML](/api_help/form/classes/cformresult/getdatabyidforhtml.php).   Параметр необязательный. По умолчанию - "false". |

### Смотрите также

* [CForm::GetMultiSelectField](/api_help/form/classes/cform/getmultiselectfield.php)

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
		<td>Ваше образование:</td>
		<td><?
			// символьный идентификатор вопроса
			$QUESTION_SID = "EDUCATION"; 
			// массив описывающий элементы списка множественного выбора
			$arMultiSelect = array (
				"reference" => array (
					"начальное",
					"средне-специальное",
					"высшее",
				),
				"reference_id" => array (
					602,
					603,
					604,
				),
				"param" => array (
					"",
					"",
					"checked", // значение по умолчанию
				)
			);
			// получим текущее значение выпадающего списка
			$arValues = CForm::GetMultiSelectValue($QUESTION_SID, $arMultiSelect, $arrVALUES);
			// выведем список множественного выбора
			echo CForm::GetMultiSelectField(
				$QUESTION_SID,           // символьный идентификатор вопроса
				$arMultiSelect,          // массив описывающий элементы списка
				$arValues,               // значения выбранных элементов списка
				10,                      // высота списка
				"class=\"inputselect\""  // стиль списка
			);      
		?></td>
	</tr>
</table>
<input type="submit" name="save" value="Сохранить">
</form>Копировать
```

Новинки документации в соцсетях: