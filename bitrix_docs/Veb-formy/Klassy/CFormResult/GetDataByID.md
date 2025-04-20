[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormResult](/api_help/form/classes/cformresult/index.php)

GetDataByID (3.3.10)

GetDataByID
===========

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
array
CFormResult::GetDataByID(
	int result_id,
	array field,
	array &result,
	array &answer
)Копировать
```

Возвращает массив, описывающий значения [ответов](/api_help/form/terms.php#answer) на [вопросы](/api_help/form/terms.php#question) или значения [полей](/api_help/form/terms.php#field) веб-формы для указанного [результата](/api_help/form/terms.php#result). Помимо этого, метод возвращает массив, содержащий [поля результата](/api_help/form/classes/cformresult/index.php). Метод нестатический.

Формат массива, возвращаемого методом:

```
Array
(
	[символьный идентификатор вопроса 1] => массив описывающий ответы на вопрос 1
		Array
		(
			[0] => массив описывающий ответ 1
				Array
				(
					[RESULT_ID]           => ID результата
					[FIELD_ID]            => ID вопроса
					[SID]                 => символьный идентификатор вопроса
					[TITLE]               => текст вопроса
					[TITLE_TYPE]          => тип текста вопроса [text|html]
					[FILTER_TITLE]        => заголовок поля фильтра
					[RESULTS_TABLE_TITLE] => заголовок столбца таблицы результатов
					[ANSWER_ID]           => ID ответа
					[ANSWER_TEXT]         => параметр ответа ANSWER_TEXT
					[ANSWER_VALUE]        => параметр ответа ANSWER_VALUE
					[USER_TEXT]           => текст введенный с клавиатуры
					[USER_DATE]           => введенная дата (если FIELD_TYPE=date)
					[USER_FILE_ID]        => ID файла (если FIELD_TYPE=[file|image])
					[USER_FILE_NAME]      => имя файла
					[USER_FILE_IS_IMAGE]  => "Y" - FIELD_TYPE=image; "N" - FIELD_TYPE=file 
					[USER_FILE_HASH]      => хэш файла (если FIELD_TYPE=file)
					[USER_FILE_SUFFIX]    => суффикс к расширению файла (если FIELD_TYPE=file)
					[USER_FILE_SIZE]      => размер файла (если FIELD_TYPE=[file|image])
					[FIELD_TYPE]          => тип ответа
					[FIELD_WIDTH]         => ширина поля ответа
					[FIELD_HEIGHT]        => высота поля ответа
					[FIELD_PARAM]         => параметр поля ответа
				)
			[1] => массив описывающий ответ 2
			[2] => массив описывающий ответ 3
			...
			[N-1] => массив описывающий ответ N
		)
	[символьный идентификатор вопроса 2] => массив описывающий ответы на вопрос 2
	[символьный идентификатор вопроса 3] => массив описывающий ответы на вопрос 3
	...
	[символьный идентификатор вопроса N] => массив описывающий ответы на вопрос N
)Копировать
```

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *result\_id* | ID результата. |
| *field* | Массив символьных идентификаторов вопросов или полей веб-формы, значения которых необходимо получить. |
| *result* | Ссылка на массив [полей результата](/api_help/form/classes/cformresult/index.php), а также некоторых [полей веб-формы](/api_help/form/classes/cform/index.php) и [полей статуса](/api_help/form/classes/cformstatus/index.php). Структура данного массива:  ``` Array ( 	[ID] => ID результата 	[TIMESTAMP_X] => время изменения результата 	[DATE_CREATE] => дата создания результата 	[FORM_ID] => ID веб-формы 	[USER_ID] => ID пользователя создавшего результат (автор) 	[USER_AUTH] => флаг авторизованности автора при создании результата [Y|N] 	[STAT_GUEST_ID] => ID посетителя создавшего результат 	[STAT_SESSION_ID] => ID сессии в которой был создан результат 	[STATUS_ID] => ID статуса в котором находится результат 	[STATUS_TITLE] => заголовок статуса в котором находится результат 	[STATUS_DESCRIPTION] => описание статуса в котором находится результат 	[STATUS_CSS] => имя CSS класса в котором находится результат 	[SID] => символьный идентификатор веб-формы 	[NAME] => заголовок веб-формы 	[IMAGE_ID] => ID изображения веб-формы 	[DESCRIPTION] => описание веб-формы 	[DESCRIPTION_TYPE] => тип описания веб-формы [text|html] )Копировать ``` |
| *answer* | Ссылка на массив, описывающий значения ответов на вопросы или значения полей веб-формы для указанного результата *result\_id*. Структура данного массива:  ``` Array ( 	[символьный идентификатор вопроса 1] => массив описывающий ответы на вопрос 1 		Array 		( 			[ID ответа 1] => массив описывающий ответ 1 				Array 				( 					[RESULT_ID]           => ID результата 					[FIELD_ID]            => ID вопроса 					[SID]                 => символьный идентификатор вопроса 					[TITLE]               => текст вопроса 					[TITLE_TYPE]          => тип текста вопроса [text|html] 					[FILTER_TITLE]        => заголовок поля фильтра 					[RESULTS_TABLE_TITLE] => заголовок столбца таблицы результатов 					[ANSWER_ID]           => ID ответа 					[ANSWER_TEXT]         => параметр ответа ANSWER_TEXT 					[ANSWER_VALUE]        => параметр ответа ANSWER_VALUE 					[USER_TEXT]           => текст введенный с клавиатуры 					[USER_DATE]           => введенная дата (если FIELD_TYPE=date) 					[USER_FILE_ID]        => ID файла (FIELD_TYPE=[file|image]) 					[USER_FILE_NAME]      => имя файла 					[USER_FILE_IS_IMAGE]  => "Y" - FIELD_TYPE=image; "N" - FIELD_TYPE=file  					[USER_FILE_HASH]      => хэш файла (если FIELD_TYPE=file) 					[USER_FILE_SUFFIX]    => суффикс к расширению файла (FIELD_TYPE=file) 					[USER_FILE_SIZE]      => размер файла (если FIELD_TYPE=[file|image]) 					[FIELD_TYPE]          => тип ответа 					[FIELD_WIDTH]         => ширина поля ответа 					[FIELD_HEIGHT]        => высота поля ответа 					[FIELD_PARAM]         => параметр поля ответа 				) 			[ID ответа 2] => массив описывающий ответ 2 			[ID ответа 3] => массив описывающий ответ 3 			... 			[ID ответа N] => массив описывающий ответ N 		) 	[символьный идентификатор вопроса 2] => массив описывающий ответы на вопрос 2 	[символьный идентификатор вопроса 3] => массив описывающий ответы на вопрос 3 	... 	[символьный идентификатор вопроса N] => массив описывающий ответы на вопрос N )Копировать ``` |

### Смотрите также

* [Поля CFormResult](/api_help/form/classes/cformresult/index.php)
* [Поля CForm](/api_help/form/classes/cform/index.php)
* [CForm::GetResultAnswerArray](/api_help/form/classes/cform/getresultanswerarray.php)

### Примеры использования

```
<?
$RESULT_ID = 189; // ID результата
$arAnswer = CFormResult::GetDataByID(
	$RESULT_ID, 
	array("VS_INTEREST"),  // вопрос "Какие области знаний вас интересуют?" 
	$arResult, 
	$arAnswer2);
// выведем поля результата
echo "<pre>"; print_r($arResult); echo "</pre>";
// выведем значения ответов
echo "<pre>"; print_r($arAnswer); echo "</pre>";
// выведем значения ответов в несколько ином формате
echo "<pre>"; print_r($arAnswer2); echo "</pre>";
?>Копировать
```

```
<?
$RESULT_ID = 189; // ID результата
// получим данные по всем вопросам
$arAnswer = CFormResult::GetDataByID(
	$RESULT_ID, 
	array(), 
	$arResult, 
	$arAnswer2);
// выведем поля результата
echo "<pre>"; print_r($arResult); echo "</pre>";
// выведем значения ответов
echo "<pre>"; print_r($arAnswer); echo "</pre>";
// выведем значения ответов в несколько ином формате
echo "<pre>"; print_r($arAnswer2); echo "</pre>";
?>Копировать
```

Новинки документации в соцсетях: