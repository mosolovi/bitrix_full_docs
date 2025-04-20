[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CForm](/api_help/form/classes/cform/index.php)

GetMultiSelectField (3.1.1)

GetMultiSelectField
===================

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
string
CForm::GetMultiSelectField(
	string question_sid,
	array list,
	array values = array(),
	mixed height = "",
	string add_to_multiselect = "class=\"inputselect\""
)Копировать
```

Возвращает HTML код списка множественного выбора, предназначенного для выбора [ответов](/api_help/form/terms.php#answer) из группы ответов типа "multiselect" на вопрос, символьный идентификатор которого передается в параметре *question\_sid*.

Метод может использоваться как в форме
создания нового [результата](/api_help/form/terms.php#result), так и в форме редактирования существующего. Метод нестатический.

**Примечание**  
Имя результирующего HTML поля будет сформировано по следующей маске:  
 **form\_multiselect\_***question\_sid***[]**

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| *question\_sid* | Символьный идентификатор [вопроса](/api_help/form/terms.php#question). |  |
| *list* | Массив ответов типа "multiselect" на вопрос *question\_sid*. Минимально требуемая структура данного массива:  ``` Array ( 	[reference] => array 	( 		[0] => заголовок ответа 1 		[1] => заголовок ответа 2 		[2] => заголовок ответа 3 		... 	) 	[reference_id] => array 	( 		[0] => ID ответа 1 		[1] => ID ответа 2 		[2] => ID ответа 3 		... 	) )Копировать ```  В данном массиве под *заголовком ответа* понимается параметр ANSWER\_TEXT [ответа](/api_help/form/terms.php#answer). |  |
| *values* | Если в данном параметре будет передан массив со значениями, совпадающими с *ID ответов*, данные ответы будут выбраны (выделены) в результирующем списке:  `<option value="значение элемента" selected>заголовок элемента</option>`   Параметр необязательный. По умолчанию - array() (пустой массив). |  |
| *height* | Высота результирующего списка множественного выбора:  `<select multiple size="height" ...>`   Параметр необязательный. По умолчанию - "class=\"inputselect\"". |  |
| *add\_to\_multiselect* | Произвольный HTML, который будет добавлен в результирующий HTML тег:  `<select add_to_multiselect ...>`   Параметр необязательный. По умолчанию - "class=\"inputselect\"". |  |

### Смотрите также

* [CForm::GetMultiSelectValue](/api_help/form/classes/cform/getmultiselectvalue.php)
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