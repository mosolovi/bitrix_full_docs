[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CForm](/api_help/form/classes/cform/index.php)

GetResultAnswerArray (3.1.1)

GetResultAnswerArray
====================

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
CForm::GetResultAnswerArray(
	int form_id,
	array &columns,
	array &answers,
	array &answers2 = array(),
	array filter = array(),
)Копировать
```

Возвращает массивы, описывающие [вопросы](/api_help/form/terms.php#question) и [поля](/api_help/form/terms.php#field) [веб-формы](/api_help/form/terms.php#form), а также [ответы на вопросы](/api_help/form/terms.php#answer). Метод нестатический.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| *form\_id* | ID формы. | Удален с 3.3.10 |
| *columns* | Параметр примет значение ссылки на массив, описывающий те вопросы и поля формы, которые:  1. активны; 2. включены в таблицу результатов.  Ключами данного массива являются ID вопросов/полей, а значениями - массив, описывающий сам вопрос/поле, в свою очередь, имеющий следующие ключи:  * **ID** - ID вопроса/поля; * **FORM\_ID** - ID формы; * **TIMESTAMP\_X** - дата изменения вопроса/поля; * **ACTIVE** - флаг активности [Y|N]; * **TITLE** - текст вопроса, либо заголовок поля; * **TITLE\_TYPE** - тип текста; * **SID** - символьный идентификатор вопроса/поля; * **C\_SORT** - порядок сортировки; * **ADDITIONAL** - если Y - то данная запись является вопросом; если N - то полем формы; * **REQUIRED** - флаг обязательности ответа на вопрос [Y|N]; * **IN\_FILTER** - флаг показывающий отражен ли вопрос/поле в фильтре формы результатов [Y|N]; * **IN\_RESULTS\_TABLE** - флаг показывающий отображается ли вопрос/поле в таблице результатов [Y|N]; * **IN\_EXCEL\_TABLE** - флаг показывающий отображается ли вопрос/поле в Excel-таблице результатов [Y|N]; * **FIELD\_TYPE** тип поля, возможны следующие значения:   + **text** - текст;   + **integer** - число;   + **date** - дата. * **IMAGE\_ID** - ID изображения в описании вопроса; * **COMMENTS** - служебный комментарий; * **FILTER\_TITLE** - заголовок поля фильтра по данному вопросу/полю; * **RESULTS\_TABLE\_TITLE** - заголовок столбца таблицы результатов.  **Пример:**  ``` Array ( 	[140] => Array 	( 		[ID] => 140 		[FORM_ID] => 4 		[TIMESTAMP_X] => 19.05.2005 11:42:04 		[ACTIVE] => Y 		[TITLE] => Фамилия, имя, отчество 		[TITLE_TYPE] => html 		[SID] => VS_NAME 		[C_SORT] => 100 		[ADDITIONAL] => N 		[REQUIRED] => Y 		[IN_FILTER] => Y 		[IN_RESULTS_TABLE] => N 		[IN_EXCEL_TABLE] => N 		[FIELD_TYPE] =>  		[IMAGE_ID] =>  		[COMMENTS] =>  		[FILTER_TITLE] =>  		[RESULTS_TABLE_TITLE] =>  	) 	[144] => Array 	( 		[ID] => 144 		[FORM_ID] => 4 		[TIMESTAMP_X] => 11.11.2004 18:11:21 		[ACTIVE] => Y 		[TITLE] => Какие области знаний вас интересуют ? 		[TITLE_TYPE] => text 		[SID] => VS_INTEREST 		[C_SORT] => 500 		[ADDITIONAL] => N 		[REQUIRED] => N 		[IN_FILTER] => Y 		[IN_RESULTS_TABLE] => Y 		[IN_EXCEL_TABLE] => Y 		[FIELD_TYPE] =>  		[IMAGE_ID] =>  		[COMMENTS] =>  		[FILTER_TITLE] =>  		[RESULTS_TABLE_TITLE] =>  	) 	... )Копировать ``` |  |
| *answers* | Параметр примет значение ссылки на массив, содержащий ответы на вопросы формы, а также значения полей формы. Ключами данного массива являются:  * **RESULT\_ID** - ID результата; * **FIELD\_ID** - ID вопроса/поля; * **SID** - символьный идентификатор вопроса/поля; * **TITLE** - текст вопроса или заголовок поля веб-формы; * **TITLE\_TYPE** - тип текста вопроса, допустимы следующие значения:   + **text** - текст;   + **html** - HTML код. * **FILTER\_TITLE** - подпись поля фильтра по данному вопросу/полю; * **RESULTS\_TABLE\_TITLE** - подпись столбца таблицы результатов; * **ANSWER\_ID** - ID ответа; * **ANSWER\_TEXT** - параметр ответа ANSWER\_TEXT, записанный в таблицу результата; * **MESSAGE** - параметр ответа ANSWER\_TEXT, хранящийся в таблице ответов (синоним ключа **ANSWER\_TEXT**); * **ANSWER\_VALUE** - параметр ответа ANSWER\_VALUE, записанный в таблицу результата; * **VALUE** - параметр ответа ANSWER\_VALUE, хранящийся в таблице ответов (синоним ключа **ANSWER\_VALUE**); * **USER\_TEXT** - текстовое значение, введенное пользователем; * **USER\_DATE** - дата, введенная пользователем (данный ключ может содержать значение, только если **FIELD\_TYPE**="date"); * **USER\_FILE\_ID** - ID файла загруженного пользователем (данный ключ может содержать значение, только если **FIELD\_TYPE**="image" или **FIELD\_TYPE**="file"); * **USER\_FILE\_NAME** - оригинальное имя загруженного файла (данный ключ может содержать значение, только если **FIELD\_TYPE**="image" или **FIELD\_TYPE**="file"); * **USER\_FILE\_IS\_IMAGE** - "Y" - если **FIELD\_TYPE**="image", "N" - если **FIELD\_TYPE**="file" * **USER\_FILE\_HASH** - уникальный хеш, используемый при показе файла (данный ключ может содержать значение, только если **FIELD\_TYPE**="file"); * **USER\_FILE\_SUFFIX** - суффикс к расширению загруженного файла (данный ключ может содержать значение, только если **FIELD\_TYPE**="file"); * **USER\_FILE\_SIZE** - размер файла в байтах (данный ключ может содержать значение, только если **FIELD\_TYPE**="image" или **FIELD\_TYPE**="file"); * **FIELD\_TYPE** - тип поля ответа, возможны следующие значения:   + **text** - однострочное текстовое поле;   + **textarea** - многострочное текстовое поле;   + **radio** - переключатель одиночного выбора;   + **checkbox** - флаг множественного выбора;   + **dropdown** - элемента выпадающего списка одиночного выбора;   + **multiselect** - элемента списка множественного выбора;   + **date** - поле для ввода дата в календарем;   + **image** - поле для ввода изображения;   + **file** - поле для ввода произвольного файла;   + **password** - однострочное поле для ввода пароля. * **FIELD\_WIDTH** - ширина поля ответа; * **FIELD\_HEIGHT** - высота поля ответа; * **FIELD\_PARAM** - параметры поля ответа.  **Пример:**  ``` Array ( 	[186] => Array 	( 		[140] => Array 		( 			[586] => Array 			( 				[RESULT_ID] => 186 				[FIELD_ID] => 140 				[SID] => VS_NAME 				[TITLE] => Фамилия, имя, отчество 				[TITLE_TYPE] => html 				[FILTER_TITLE] =>  				[RESULTS_TABLE_TITLE] =>  				[ANSWER_ID] => 586 				[ANSWER_TEXT] =>   				[MESSAGE] =>   				[ANSWER_VALUE] =>  				[VALUE] =>  				[USER_TEXT] => Иванов Дмитрий Витальевич 				[USER_DATE] =>  				[USER_FILE_ID] =>  				[USER_FILE_NAME] =>  				[USER_FILE_IS_IMAGE] =>  				[USER_FILE_HASH] =>  				[USER_FILE_SUFFIX] =>  				[USER_FILE_SIZE] =>  				[FIELD_TYPE] => text 				[FIELD_WIDTH] => 50 				[FIELD_HEIGHT] => 0 				[FIELD_PARAM] =>  			) 		) 		[144] => Array 		( 			[594] => Array 			( 				[RESULT_ID] => 186 				[FIELD_ID] => 144 				[SID] => VS_INTEREST 				[TITLE] => Какие области знаний вас интересуют ? 				[TITLE_TYPE] => text 				[FILTER_TITLE] =>  				[RESULTS_TABLE_TITLE] =>  				[ANSWER_ID] => 594 				[ANSWER_TEXT] => иностранные языки 				[MESSAGE] => иностранные языки 				[ANSWER_VALUE] => 4 				[VALUE] => 4 				[USER_TEXT] =>  				[USER_DATE] =>  				[USER_FILE_ID] =>  				[USER_FILE_NAME] =>  				[USER_FILE_IS_IMAGE] =>  				[USER_FILE_HASH] =>  				[USER_FILE_SUFFIX] =>  				[USER_FILE_SIZE] =>  				[FIELD_TYPE] => checkbox 				[FIELD_WIDTH] => 0 				[FIELD_HEIGHT] => 0 				[FIELD_PARAM] =>  			) 			[595] => Array 			( 				[RESULT_ID] => 186 				[FIELD_ID] => 144 				[SID] => VS_INTEREST 				[TITLE] => Какие области знаний вас интересуют ? 				[TITLE_TYPE] => text 				[FILTER_TITLE] =>  				[RESULTS_TABLE_TITLE] =>  				[ANSWER_ID] => 595 				[ANSWER_TEXT] => програмирование 				[MESSAGE] => програмирование 				[ANSWER_VALUE] => 5 				[VALUE] => 5 				[USER_TEXT] =>  				[USER_DATE] =>  				[USER_FILE_ID] =>  				[USER_FILE_NAME] =>  				[USER_FILE_IS_IMAGE] =>  				[USER_FILE_HASH] =>  				[USER_FILE_SUFFIX] =>  				[USER_FILE_SIZE] =>  				[FIELD_TYPE] => checkbox 				[FIELD_WIDTH] => 0 				[FIELD_HEIGHT] => 0 				[FIELD_PARAM] => SELECTED class=inputcheckbox 			) 		) 		... 	) 	... )Копировать ``` |  |
| *answers2* | Параметр примет значение ссылки на массив, содержащий, по сути, те же данные, что и массив answers, но имеющий несколько другую структуру.    **Пример:**  ``` Array ( 	[186] => Array 	( 		[VS_NAME] => Array 		( 			[0] => Array 			( 				[RESULT_ID] => 186 				[FIELD_ID] => 140 				[SID] => VS_NAME 				[TITLE] => Фамилия, имя, отчество 				[TITLE_TYPE] => html 				[FILTER_TITLE] =>  				[RESULTS_TABLE_TITLE] =>  				[ANSWER_ID] => 586 				[ANSWER_TEXT] =>  				[MESSAGE] =>   				[ANSWER_VALUE] =>  				[VALUE] =>  				[USER_TEXT] => Иванов Дмитрий Витальевич 				[USER_DATE] =>  				[USER_FILE_ID] =>  				[USER_FILE_NAME] =>  				[USER_FILE_IS_IMAGE] =>  				[USER_FILE_HASH] =>  				[USER_FILE_SUFFIX] =>  				[USER_FILE_SIZE] =>  				[FIELD_TYPE] => text 				[FIELD_WIDTH] => 50 				[FIELD_HEIGHT] => 0 				[FIELD_PARAM] =>  			) 		) 		[VS_INTEREST] => Array 		( 			[0] => Array 			( 				[RESULT_ID] => 186 				[FIELD_ID] => 144 				[SID] => VS_INTEREST 				[TITLE] => Какие области знаний вас интересуют ? 				[TITLE_TYPE] => text 				[FILTER_TITLE] =>  				[RESULTS_TABLE_TITLE] =>  				[ANSWER_ID] => 594 				[ANSWER_TEXT] => иностранные языки 				[MESSAGE] => иностранные языки 				[ANSWER_VALUE] => 4 				[VALUE] => 4 				[USER_TEXT] =>  				[USER_DATE] =>  				[USER_FILE_ID] =>  				[USER_FILE_NAME] =>  				[USER_FILE_IS_IMAGE] =>  				[USER_FILE_HASH] =>  				[USER_FILE_SUFFIX] =>  				[USER_FILE_SIZE] =>  				[FIELD_TYPE] => checkbox 				[FIELD_WIDTH] => 0 				[FIELD_HEIGHT] => 0 				[FIELD_PARAM] =>  			) 			[1] => Array 			( 				[RESULT_ID] => 186 				[FIELD_ID] => 144 				[SID] => VS_INTEREST 				[TITLE] => Какие области знаний вас интересуют ? 				[TITLE_TYPE] => text 				[FILTER_TITLE] =>  				[RESULTS_TABLE_TITLE] =>  				[ANSWER_ID] => 595 				[ANSWER_TEXT] => програмирование 				[MESSAGE] => програмирование 				[ANSWER_VALUE] => 5 				[VALUE] => 5 				[USER_TEXT] =>  				[USER_DATE] =>  				[USER_FILE_ID] =>  				[USER_FILE_NAME] =>  				[USER_FILE_IS_IMAGE] =>  				[USER_FILE_HASH] =>  				[USER_FILE_SUFFIX] =>  				[USER_FILE_SIZE] =>  				[FIELD_TYPE] => checkbox 				[FIELD_WIDTH] => 0 				[FIELD_HEIGHT] => 0 				[FIELD_PARAM] => SELECTED class=inputcheckbox 			) 		) 		... 	) 	... )Копировать ``` |  |
| *filter* | Массив для фильтрации выбираемых значений. Необязательный параметр. В массиве допустимы следующие ключи:  * **RESULT\_ID**\* - ID результата (по умолчанию будет искаться точное совпадение); * RESULT\_ID\_EXACT\_MATCH - если значение равно "N", то при фильтрации по **RESULT\_ID** будет искаться вхождение; * **FIELD\_ID**\* - ID вопроса/поля (по умолчанию будет искаться точное совпадение); * **FIELD\_ID\_EXACT\_MATCH** - если значение равно "N", то при фильтрации по **FIELD\_ID** будет искаться вхождение; * **FIELD\_SID**\* - символьный код вопроса/поля (по умолчанию будет искаться вхождение); * **FIELD\_SID\_EXACT\_MATCH** - если значение равно "Y", то при фильтрации по **FIELD\_SID** будет искаться точное совпадение; * **IN\_RESULTS\_TABLE** - если значение равно "Y", то ответы на вопрос (либо значения поля веб-формы) будет отображены в таблице результатов; * **IN\_EXCEL\_TABLE** - если значение равно "Y", то ответы на вопрос (либо значения поля веб-формы) будет отображены в Excel таблице результатов.  \* - допускается сложная логика. |  |
| *arrAnswersVarname* |  | 3.3.10. Удален с версии 4.0.4 |
| web\_form\_id | ID формы. | 3.3.10 |
| *arrAnswersSID* |  | 4.0.4 |

### Смотрите также

* [CFormResult::GetDataByID](/api_help/form/classes/cformresult/getdatabyid.php)
* [CFormField::GetList](/api_help/form/classes/cformfield/getlist.php)
* [CFormAnswer::GetList](/api_help/form/classes/cformanswer/getlist.php)

### Примеры использования

```
// получим данные по результату ID=145
CForm::GetResultAnswerArray(
	$FORM_ID, 
	$arrColumns, 
	$arrAnswers, 
	$arrAnswersVarname, 
	array("RESULT_ID" => "145")
);
echo "<pre>";
echo "arrColumns:";
print_r($arrColumns);
echo "arrAnswers:";
print_r($arrAnswers);
echo "arrAnswersVarname:";
print_r($arrAnswersVarname);
echo "</pre>";Копировать
```

Новинки документации в соцсетях: