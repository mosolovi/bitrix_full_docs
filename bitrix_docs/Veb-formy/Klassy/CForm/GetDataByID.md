[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CForm](/api_help/form/classes/cform/index.php)

GetDataByID (3.1.1)

GetDataByID
===========

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
mixed
CForm::GetDataByID(
	int form_id,
	array &form,
	array &questions,
	array &answers,
	array &dropdown,
	array &multiselect,
	string get_fields = "Y"
)Копировать
```

Возвращает массивы, описывающие [веб-форму](/api_help/form/terms.php#form), [вопросы](/api_help/form/terms.php#question) и поля для [ответов](/api_help/form/terms.php#answer). Сам метод возвращает ID веб-формы в случае положительного результата, в противном случае - "false". Метод нестатический.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| *form\_id* | ID веб-формы. С версии 3.3.10 переименован в *web\_form\_id* |  |
| *form* | Массив, содержащий параметры формы. Ключи данного массива:  * **ID** - ID веб-формы; * **TIMESTAMP\_X** - дата изменения; * **NAME** - наименование; * **SID** - символьный идентификатор; * **BUTTON** - подпись к кнопке при редактировании результата или создании нового результата; * **C\_SORT** - порядок сортировки; * **IMAGE\_ID** - ID изображения; * **DESCRIPTION** - описание; * **DESCRIPTION\_TYPE** - тип описания, допустимы следующие значения:   + **text** - текст;   + **html** - HTML код. * **MAIL\_EVENT\_TYPE** - идентификатор типа почтового события; * **FILTER\_RESULT\_TEMPLATE** - путь относительно корня к скрипту, отображающему фильтр по результатам веб-форм в административной части модуля; * **TABLE\_RESULT\_TEMPLATE** - путь относительно корня к скрипту, отображающему таблицу результатов веб-формы в административной части модуля; * **STAT\_EVENT1** - идентификатор event1 типа события для модуля "Статистика"; * **STAT\_EVENT2** - идентификатор event2 типа события для модуля "Статистика"; * **STAT\_EVENT3** - дополнительный параметр event3 события для модуля "Статистика"; * **QUESTIONS** - количество вопросов формы; * **C\_FIELDS** - количество полей формы; * **STATUSES** - количество статусов.  **Пример:**  ``` Array ( 	[ID] => 4 	[TIMESTAMP_X] => 18.05.2005 12:17:05 	[NAME] => Анкета посетителя сайта 	[SID] => ANKETA 	[BUTTON] => Сохранить 	[C_SORT] => 300 	[IMAGE_ID] => 1053 	[DESCRIPTION] => Тестовая форма. 	[DESCRIPTION_TYPE] => text 	[MAIL_EVENT_TYPE] => FORM_FILLING_ANKETA 	[FILTER_RESULT_TEMPLATE] =>  	[TABLE_RESULT_TEMPLATE] =>  	[STAT_EVENT1] => form 	[STAT_EVENT2] => anketa 	[STAT_EVENT3] =>  	[C_FIELDS] => 1 	[QUESTIONS] => 6 	[STATUSES] => 4 )Копировать ``` |  |
| *questions* | Массив, содержащий вопросы и поля формы. Ключами данного массива являются идентификаторы вопросов/полей, а значениями - массивы, каждый из которых описывает один вопрос/поле.  Ключи массива, описывающего один вопрос/поле:  * **ID** - ID вопроса/поля; * **FORM\_ID** - ID формы; * **TIMESTAMP\_X** - дата изменения вопроса/поля; * **ACTIVE** - флаг активности [Y|N]; * **TITLE** - текст вопроса либо заголовок поля; * **TITLE\_TYPE** - тип текста; * **SID** - символьный идентификатор вопроса/поля; * **C\_SORT** - порядок сортировки; * **ADDITIONAL** - если  **Y** - то данная запись является вопросом; если  **N** - то полем формы; * **REQUIRED** - флаг обязательности ответа на вопрос [Y|N]; * **IN\_FILTER** - флаг, показывающий отражен ли вопрос/поле в фильтре формы результатов [Y|N]; * **IN\_RESULTS\_TABLE** - флаг, показывающий отображается ли вопрос/поле в таблице результатов [Y|N]; * **IN\_EXCEL\_TABLE** - флаг, показывающий отображается ли вопрос/поле в Excel-таблице результатов [Y|N]; * **FIELD\_TYPE** тип поля, возможны следующие значения:   + **text** - текст;   + **integer** - число;   + **date** - дата. * **IMAGE\_ID** - ID изображения в описании вопроса; * **COMMENTS** - служебный комментарий; * **FILTER\_TITLE** - заголовок поля фильтра по данному вопросу/полю; * **RESULTS\_TABLE\_TITLE** - заголовок столбца таблицы результатов.  **Пример:**  ``` Array ( 	[VS_NAME] => Array 	( 		[ID] => 140 		[FORM_ID] => 4 		[TIMESTAMP_X] => 28.08.2003 11:45:57 		[ACTIVE] => Y 		[TITLE] => Фамилия, имя, отчество 		[TITLE_TYPE] => html 		[SID] => VS_NAME 		[C_SORT] => 100 		[ADDITIONAL] => N 		[REQUIRED] => Y 		[IN_FILTER] => Y 		[IN_RESULTS_TABLE] => Y 		[IN_EXCEL_TABLE] => Y 		[FIELD_TYPE] =>  		[IMAGE_ID] =>  		[COMMENTS] =>  		[FILTER_TITLE] => ФИО 		[RESULTS_TABLE_TITLE] => ФИО 	) 	[VS_MARRIED] => Array 	( 		[ID] => 143 		[FORM_ID] => 4 		[TIMESTAMP_X] => 11.11.2004 18:13:21 		[ACTIVE] => Y 		[TITLE] => Вы женаты / замужем ? 		[TITLE_TYPE] => text 		[SID] => VS_MARRIED 		[C_SORT] => 400 		[ADDITIONAL] => N 		[REQUIRED] => Y 		[IN_FILTER] => Y 		[IN_RESULTS_TABLE] => Y 		[IN_EXCEL_TABLE] => Y 		[FIELD_TYPE] =>  		[IMAGE_ID] =>  		[COMMENTS] =>  		[FILTER_TITLE] => Семейный статус 		[RESULTS_TABLE_TITLE] => Семейный статус 	) 	...     )Копировать ``` |  |
| *answers* | Массив, содержащие данные по полям для ответа на вопросы веб-формы. Ключами данного массива являются идентификаторы вопросов, а значениями - массивы, каждый из которых описывает набор полей для ответа на вопрос.  Структура массива, описывающего одно поле ответа:  * **ID** - ID поля для ответа; * **FIELD\_ID** - ID вопроса формы; * **TIMESTAMP\_X** - дата изменения поля; * **MESSAGE** - текст [ANSWER\_TEXT]; * **C\_SORT** - порядок сортировки; * **ACTIVE** - флаг активности [Y|N]; * **VALUE** - значение [ANSWER\_VALUE]; * **FIELD\_TYPE** - тип поля ответа, допустимы следующие значения:   + **text** - однострочное текстовое поле;   + **textarea** - многострочное текстовое поле;   + **radio** - переключатель одиночного выбора;   + **checkbox** - флаг множественного выбора;   + **dropdown** - элемента выпадающего списка одиночного выбора;   + **multiselect** - элемента списка множественного выбора;   + **date** - поле для ввода дата в календарем;   + **image** - поле для ввода изображения;   + **file** - поле для ввода произвольного файла;   + **password** - однострочное поле для ввода пароля. * **FIELD\_WIDTH** - ширина поля ответа; * **FIELD\_HEIGHT** - высота поля ответа; * **FIELD\_PARAM** - параметры поля ответа.  **Пример**  ``` Array ( 	[VS_NAME] => Array 	( 		[0] => Array 		( 			[ID] => 586 			[FIELD_ID] => 140 			[TIMESTAMP_X] => 2003-08-28 11:45:57 			[MESSAGE] =>   			[C_SORT] => 100 			[ACTIVE] => Y 			[VALUE] =>  			[FIELD_TYPE] => text 			[FIELD_WIDTH] => 50 			[FIELD_HEIGHT] => 0 			[FIELD_PARAM] =>  		) 	) 	[VS_MARRIED] => Array 	( 		[0] => Array 		( 			[ID] => 589 			[FIELD_ID] => 143 			[TIMESTAMP_X] => 2004-11-11 18:13:21 			[MESSAGE] => да 			[C_SORT] => 100 			[ACTIVE] => Y 			[VALUE] =>  			[FIELD_TYPE] => radio 			[FIELD_WIDTH] => 0 			[FIELD_HEIGHT] => 0 			[FIELD_PARAM] => SELECTED class="inputradio" 		) 		[1] => Array 		( 			[ID] => 590 			[FIELD_ID] => 143 			[TIMESTAMP_X] => 2004-11-11 18:13:21 			[MESSAGE] => нет 			[C_SORT] => 200 			[ACTIVE] => Y 			[VALUE] =>  			[FIELD_TYPE] => radio 			[FIELD_WIDTH] => 0 			[FIELD_HEIGHT] => 0 			[FIELD_PARAM] =>  		) 	) 	... )Копировать ``` |  |
| *dropdown* | Массив, предназначенный для построения выпадающих списков одиночного выбора; содержит данные по всем полям ответа типа  **dropdown**.   **Пример:**  ``` Array ( 	[VS_AGE] => Array 	( 		[reference] => Array 		( 			[0] => - 			[1] => 10-19 			[2] => 20-29 			[3] => 30-39 			[4] => 40-49 			[5] => 50-59 			[6] => 60 и старше 		) 		[reference_id] => Array 		( 			[0] => 608 			[1] => 596 			[2] => 597 			[3] => 598 			[4] => 599 			[5] => 600 			[6] => 601 		) 		[param] => Array 		( 			[0] => NOT_ANSWER 			[1] =>  			[2] => SELECTED 			[3] =>  			[4] =>  			[5] =>  			[6] =>  		) 	) 	... )Копировать ``` |  |
| *multiselect* | Массив, предназначенный для построения списков множественного выбора; содержит данные по всем полям для ответа типа  **multiselect**.   **Пример:**  ``` Array ( 	[VS_EDUCATION] => Array 	( 		[reference] => Array 		( 			[0] => начальное 			[1] => средне-специальное 			[2] => высшее 			[3] => ясли с отличием 		) 		[reference_id] => Array 		( 			[0] => 602 			[1] => 603 			[2] => 604 			[3] => 605 		) 		[param] => Array 		( 			[0] =>  			[1] =>  			[2] => SELECTED 			[3] =>  		) 	) 	... ) Копировать ``` |  |
| *get\_fields* | Если значение данного параметра равно "Y", то в массиве *questions* будут представлены только поля формы.  Если значение равно "" - вопросы и поля формы.  В остальных случаях - в массиве *questions* будут описаны только вопросы формы.    Параметр необязательный. По умолчанию - "N" (не добавлять в массив *questions* данные о полях веб-формы). |  |
| active | Необязательный параметр. | 5.1.1 |

### Смотрите также

* [CForm::GetResultAnswerArray](/api_help/form/classes/cform/getresultanswerarray.php)

### Примеры использования

```
<?
if (CForm::GetDataByID($FORM_ID, 
	$form, 
	$questions, 
	$answers, 
	$dropdown, 
	$multiselect))
{
	echo "<pre>";
		print_r($form);
		print_r($questions);
		print_r($answers);
		print_r($dropdown);
		print_r($multiselect);
	echo "</pre>";
}
?>Копировать
```

Новинки документации в соцсетях: