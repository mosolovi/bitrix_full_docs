[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormField](/api_help/form/classes/cformfield/index.php)

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
CFormField::Set(
	array fields,
	mixed field_id = false,
	string check_rights = "Y"
)Копировать
```

Добавляет новый [вопрос](/api_help/form/terms.php#question)/[поле](/api_help/form/terms.php#field) или обновляет существующий. Возвращает ID обновленного или добавленного [вопроса](/api_help/form/terms.php#question)/[поля](/api_help/form/terms.php#field) в случае положительного результата, в противном случае - "false". Метод нестатический.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| *fields* | Массив значений, в качестве ключей массива допустимы:  * **SID**\* - символьный идентификатор [вопроса](/api_help/form/terms.php#question)/[поля](/api_help/form/terms.php#field); * **FORM\_ID**\* - ID [веб-формы](/api_help/form/terms.php#form); * **ACTIVE** - флаг активности; допустимы следующие значения:   + **Y** - [вопрос](/api_help/form/terms.php#question)/[поле](/api_help/form/terms.php#field) активен;   + **N** - [вопрос](/api_help/form/terms.php#question)/[поле](/api_help/form/terms.php#field) не активен (по умолчанию). * **ADDITIONAL** - допустимы следующие значения:   + **Y** - данная запись является [полем](/api_help/form/terms.php#field) веб-формы;   + **N** - данная запись является [вопросом](/api_help/form/terms.php#question) веб-формы (по умолчанию). * **FIELD\_TYPE**\* - тип [поля](/api_help/form/terms.php#field), допустимые следующие значения:   + **text** - текст;   + **integer** - число;   + **date** - дата. * **TITLE** - текст [вопроса](/api_help/form/terms.php#question) либо заголовок [поля](/api_help/form/terms.php#field). * **TITLE\_TYPE**\* - тип [вопроса](/api_help/form/terms.php#question); допустимы следующие значения:   + **text** - текст;   + **html** - HTML код. * **C\_SORT** - порядок сортировки; * **REQUIRED**\* - флаг обязательности ответа на [вопрос](/api_help/form/terms.php#question):   + **Y** - ответ на данный [вопрос](/api_help/form/terms.php#question) обязателен;   + **N** - ответ на данный [вопрос](/api_help/form/terms.php#question) обязателен (по умолчанию). * **FILTER\_TITLE** - подпись к полю фильтра; * **IN\_RESULTS\_TABLE** - флаг вхождения в HTML таблицу результатов:   + **Y** - ответ на данный [вопрос](/api_help/form/terms.php#question) либо значения [поля](/api_help/form/terms.php#field) веб-формы отражены в HTML таблице результатов;   + **N** - ответ на данный [вопрос](/api_help/form/terms.php#question) либо значения [поля](/api_help/form/terms.php#field) веб-формы отражены в HTML таблице результатов (по умолчанию). * **IN\_EXCEL\_TABLE** - флаг вхождения в Excel таблицу [результатов](/api_help/form/terms.php#result):   + **Y** - ответ на данный [вопрос](/api_help/form/terms.php#question) либо значения [поля](/api_help/form/terms.php#field) веб-формы отражены в Excel таблице [результатов](/api_help/form/terms.php#result)   + **N** - ответ на данный [вопрос](/api_help/form/terms.php#question) либо значения [поля](/api_help/form/terms.php#field) веб-формы отражены в Excel таблице [результатов](/api_help/form/terms.php#result) (по умолчанию). * **RESULTS\_TABLE\_TITLE** - заголовок столбца в таблицах результатов; * **COMMENTS** - служебный комментарий; * **arIMAGE**\*\* - массив, описывающий изображение [вопроса](/api_help/form/terms.php#question), допустимы следующие ключи этого массива:   + **name** - имя файла;   + **size** - размер файла;   + **tmp\_name** - временный путь на сервере;   + **type** - тип загружаемого файла;   + **del** - если значение равно "Y", то изображение будет удалено;   + **MODULE\_ID** - идентификатор модуля "Веб-формы" - **form** * **arANSWER**\*\* - массив, описывающий [ответы](/api_help/form/terms.php#answer) на [вопрос](/api_help/form/terms.php#question), со следующей структурой:    ```   Array   (   	[0] => Array   	(   		[ID] => ID   		[DELETE] => флаг необходимости удаления [Y|N]   		[MESSAGE] => параметр ANSWER_TEXT   		[VALUE] => параметр ANSWER_VALUE   		[C_SORT] => порядок сортировки   		[ACTIVE] => флаг активности [Y|N]   		[FIELD_TYPE] => тип, допустимы следующие значения:   			text - однострочное текстовое поле   			textarea - многострочное текстовое поле   			radio* - переключатель одиночного выбора (radio-кнопка)   			checkbox* - флаг множественного выбора (checkbox)   			dropdown* - элемент выпадающего списка одиночного выбора   			multiselect* - элемент списка множественного выбора   			date - поле для ввода даты   			image - поле для загрузки изображения   			file - поле для загрузки произвольного файла   			password - поле для ввода пароля   		[FIELD_WIDTH] => ширина поля ввода   		[FIELD_HEIGHT] => высота поля ввода   		[FIELD_PARAM] => дополнительные параметры;    			допустимо использование любого HTML кода;    			для типов помеченных символом * допустимо использование    			следующих зарезервированных строк:   			checked - ответ будет выбран (отмечен)                              по умолчанию (синоним - selected)   			not_answer - выбор данного ответа не означает,                             что был дан ответ на вопрос                              (как правило это первый элемент выпадающего списка и                             важно при REQUIRED="Y")   	)   	[1] => массив описывающий следующий ответ   	...   )Копировать   ``` * **arFILTER\_USER**\*\* - массив полей фильтра для фильтрации по значению [ответа](/api_help/form/terms.php#answer), введенному с клавиатуры пользователем при заполнении веб-формы; в данном массиве допустимы следующие значения:   + **text** - [текстовое поле](/api_help/form/classes/cform/gettextfilter.php) фильтра;   + **integer** - поля фильтра для [числового интервала](/api_help/form/classes/cform/getnumberfilter.php);   + **date** - поля фильтра для [интервала дат](/api_help/form/classes/cform/getdatefilter.php);   + **exist** - поле для фильтрации по [факту существования](/api_help/form/classes/cform/getexistflagfilter.php) введенного ответа. * **arFILTER\_ANSWER\_TEXT**\*\* - массив полей фильтра для фильтрации по параметру [ответа](/api_help/form/terms.php#answer) ANSWER\_TEXT; в данном массиве допустимы следующие значения:   + **text** - [текстовое поле](/api_help/form/classes/cform/gettextfilter.php) фильтра;   + **integer** - поля фильтра для [числового интервала](/api_help/form/classes/cform/getnumberfilter.php);   + **dropdown** - [выпадающий список одиночного выбора](/api_help/form/classes/cform/getdropdownfilter.php);   + **exist** - поле для фильтрации по [факту существования](/api_help/form/classes/cform/getexistflagfilter.php). * **arFILTER\_ANSWER\_VALUE**\*\* - массив полей фильтра для фильтрации по параметру [ответа](/api_help/form/terms.php#answer) ANSWER\_VALUE; в данном массиве допустимы следующие значения:   + **text** - [текстовое поле](/api_help/form/classes/cform/gettextfilter.php) фильтра;   + **integer** - поля фильтра для [числового интервала](/api_help/form/classes/cform/getnumberfilter.php);   + **dropdown** - [выпадающий список одиночного выбора](/api_help/form/classes/cform/getdropdownfilter.php);   + **exist** - поле для фильтрации по [факту существования](/api_help/form/classes/cform/getexistflagfilter.php). * **arFILTER\_FIELD**\* - массив полей фильтра для фильтрации по значению [поля веб-формы](/api_help/form/terms.php#field):   + **text** - [текстовое поле](/api_help/form/classes/cform/gettextfilter.php) фильтра;   + **integer** - поля фильтра для [числового интервала](/api_help/form/classes/cform/getnumberfilter.php);   + **date** - поля фильтра для [интервала дат](/api_help/form/classes/cform/getdatefilter.php).   \* - обязательно к заполнению;  \* - заполняется **только** для [полей веб-формы](/api_help/form/terms.php#field);  \*\* - заполняется **только** для [вопросов веб-формы](/api_help/form/terms.php#question). |  |
| *field\_id* | ID обновляемого [вопроса](/api_help/form/terms.php#question)/[поля](/api_help/form/terms.php#field). Параметр необязательный. По умолчанию - "false" (добавление нового [вопроса](/api_help/form/terms.php#question)/[поля](/api_help/form/terms.php#field)). |  |
| *check\_rights* | Флаг необходимости проверки прав текущего пользователя. Возможны следующие значения:  * **Y** - права необходимо проверить; * **N** - право не нужно проверять.  Для добавления нового [вопроса](/api_help/form/terms.php#question)/[поля](/api_help/form/terms.php#field) или обновления их параметров необходимо иметь право **[30] Полный доступ** на веб-форму указанную в *fields*["**FORM\_ID**"].  Параметр необязательный. По умолчанию - "Y" (права необходимо проверить). |  |
| *update\_filter* | Необязательный параметр. Значение по умолчанию - "Y". | 8.0.3 |

### Смотрите также

* [Поля CFormField](/api_help/form/classes/cformfield/index.php)
* [Права на веб-форму](/api_help/form/permissions.php#form)
* [CFile::MakeFileArray](/api_help/main/reference/cfile/makefilearray.php)

### Примеры использования

```
<?
/*************************************************
         Добавление вопроса веб-формы
*************************************************/
// создадим массив описывающий изображение 
// находящееся в файле на сервере
$arIMAGE = CFile::MakeFileArray($_SERVER["DOCUMENT_ROOT"]."/images/question.gif");
$arIMAGE["MODULE_ID"] = "form";
// формируем массив ответов
$arANSWER = array();
$arANSWER[] = array(
	"MESSAGE"     => "да",                           // параметр ANSWER_TEXT
	"C_SORT"      => 100,                            // порядок фортировки 
	"ACTIVE"      => "Y",                            // флаг активности
	"FIELD_TYPE"  => "radio",                        // тип ответа
	"FIELD_PARAM" => "checked class=\"inputradio\""  // параметры ответа
);
$arANSWER[] = array(
	"MESSAGE"     => "нет",
	"C_SORT"      => 200,
	"ACTIVE"      => "Y",
	"FIELD_TYPE"  => "radio"
);
// формируем массив полей
$arFields = array( 
	"FORM_ID"              => 4,                     // ID веб-формы
	"ACTIVE"               => "Y",                     // флаг активности
	"TITLE"                => "Вы женаты/замужем ?", // текст вопроса
	"TITLE_TYPE"           => "text",                // тип текста вопроса
	"SID"                  => "VS_MARRIED",          // символьный идентификатор вопроса
	"C_SORT"               => 400,                   // порядок сортировки
	"ADDITIONAL"           => "N",                   // мы добавляем вопрос веб-формы
	"REQUIRED"             => "Y",                   // ответ на данный вопрос обязателен
	"IN_RESULTS_TABLE"     => "Y",                   // добавить в HTML таблицу результатов
	"IN_EXCEL_TABLE"       => "Y",                   // добавить в Excel таблицу результатов
	"FILTER_TITLE"         => "Женат/замужем",       // подпись к полю фильтра
	"RESULTS_TABLE_TITLE"  => "Женат/замужем",       // заголовок столбца фильтра
	"arIMAGE"              => $arIMAGE,              // изображение вопроса
	"arFILTER_ANSWER_TEXT" => array("dropdown"),     // тип фильтра по ANSWER_TEXT
	"arANSWER"             => $arANSWER,             // набор ответов
);
// добавим новый вопрос
$NEW_ID = CFormField::Set($arFields);
if ($NEW_ID>0) echo "Добавлен вопрос с ID=".$NEW_ID;
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
/*************************************************
          Добавление поля веб-формы
*************************************************/
$arFields = array( 
	"FORM_ID"             => 4
	"ACTIVE"              => "Y",
	"TITLE"               => "Рассчитанная стоимость",
	"SID"                 => "VS_PRICE",
	"C_SORT"              => 1000,
	"ADDITIONAL"          => "Y",
	"IN_RESULTS_TABLE"    => "Y",
	"IN_EXCEL_TABLE"      => "Y",
	"FIELD_TYPE"          => "text",
	"FILTER_TITLE"        => "Стоимость",
	"RESULTS_TABLE_TITLE" => "Стоимость",
	"arFILTER_FIELD"      => array("text")
);
// добавим новое поле
$NEW_ID = CFormField::Set($arFields);
if ($NEW_ID>0) echo "Добавлено поле с ID=".$NEW_ID;
else // ошибка
{
	// выводим текст ошибки
	global $strError;
	echo $strError;
}
?>Копировать
```

Новинки документации в соцсетях: