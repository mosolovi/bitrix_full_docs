[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormAnswer](/api_help/form/classes/cformanswer/index.php)

Set (4.0.4)

Set
===

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
mixed
CFormAnswer::Set(
	array fields,
	mixed answer_id = false,
	mixed current_question_id = false
)Копировать
```

Добавляет новый [ответ](/api_help/form/terms.php#answer) или обновляет существующий. Возвращает ID обновленного или добавленного [ответа](/api_help/form/terms.php#answer) в случае положительного результата, в противном случае - "false". Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *fields* | Массив значений, в качестве ключей массива допустимы:  * **QUESTION\_ID**\* - ID [вопроса](/api_help/form/terms.php#question) * **MESSAGE**\* - значение параметра [ответа](/api_help/form/terms.php#answer) ANSWER\_TEXT; * **VALUE** - значение параметра [ответа](/api_help/form/terms.php#answer) ANSWER\_VALUE; * **C\_SORT** - порядок сортировки; * **ACTIVE** - флаг активности, допустимы следующие значения:   + **Y** - ответ активен;   + **N** - ответ не активен (по умолчанию). * **FIELD\_TYPE** - тип поля [ответа](/api_help/form/terms.php#answer), допустимы следующие значения:   + **text** - однострочное текстовое поле;   + **textarea** - многострочное текстовое поле;   + **radio** - переключатель одиночного выбора (radio-кнопка);   + **checkbox** - флаг множественного выбора (checkbox);   + **dropdown** - элемент выпадающего списка одиночного выбора;   + **multiselect** - элемент списка множественного выбора;   + **date** - поле для ввода даты;   + **image** - поле для загрузки изображения;   + **file** - поле для загрузки произвольного файла;   + **password** - поле для ввода пароля. * **FIELD\_WIDTH** - ширина поля [ответа](/api_help/form/terms.php#answer); * **FIELD\_HEIGHT** - высота поля [ответа](/api_help/form/terms.php#answer); * **FIELD\_PARAM** - параметр поля [ответа](/api_help/form/terms.php#answer).  \* - обязательные поля. |
| *answer\_id* | ID обновляемого [ответа](/api_help/form/terms.php#answer).  Параметр необязательный. По умолчанию - "false" (добавление нового [ответа](/api_help/form/terms.php#answer)). |
| *current\_question\_id* | ID [вопроса](/api_help/form/terms.php#question), к которому приписан обновляемый [ответ](/api_help/form/terms.php#answer). Указание данного параметра позволяет ускорить выполнение метода.  Параметр необязательный. По умолчанию - "false". |

### Смотрите также

* [Поля CFormAnswer](/api_help/form/classes/cformanswer/index.php)

### Примеры использования

```
<?
$QUESTION_ID = 140; // ID вопроса "Фамилия, имя, отчество"
$arFields = array(
	"QUESTION_ID"   => $QUESTION_ID,
	"MESSAGE"       => " ",
	"C_SORT"        => 100,
	"ACTIVE"        => "Y",
	"FIELD_TYPE"    => "text",
	"FIELD_WIDTH"   => "40"
);
$NEW_ID = CFormAnswer::Set($arFields);
if ($NEW_ID>0) echo "Успешно добавлен ID=".$NEW_ID;
else // ошибка
{
	// выводим текст ошибки
	global $strError;
	echo $strError;
}
?>Копировать
```

```
<?
$QUESTION_ID = 143; // ID вопроса "Вы женаты/замужем?"
$arFields = array(
	"QUESTION_ID"      => $QUESTION_ID,
	"MESSAGE"       => "да",
	"C_SORT"        => 100,
	"ACTIVE"        => "Y",
	"FIELD_TYPE"    => "radio",
	"FIELD_PARAM"   => "checked"
);
CFormAnswer::Set($arFields);
$arFields = array(
	"QUESTION_ID"      => $QUESTION_ID,
	"MESSAGE"       => "нет",
	"C_SORT"        => 200,
	"ACTIVE"        => "Y",
	"FIELD_TYPE"    => "radio"
);
CFormAnswer::Set($arFields);
?>Копировать
```

Новинки документации в соцсетях: