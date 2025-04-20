[Опросы, голосования](/api_help/vote/index.php)

[Функции](/api_help/vote/function/index.php)

GetVoteDataByID (3.0.1)

GetVoteDataByID
===============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
GetVoteDataByID( 
	int VOTE_ID, 
	array &arChannel, 
	array &arVote, 
	array &arQuestions, 
	array &arAnswers, 
	array &arDropDown, 
	array &arMultiSelect, 
	array &arGroupAnswers, 
	string getGroupAnswers
)Копировать
```

Функция возвращает ID опроса в случае, если такой опрос был найден в базе, а также массивы описывающие опрос.

#### Параметры функции

| Параметр | Описание | С версии |
| --- | --- | --- |
| VOTE\_ID | ID опроса. |  |
| arChannel | Массив описывающий группу заданного опроса.  Индексы массива:- **ID** - ID группы - **SYMBOLIC\_NAME** - символическое имя - **ACTIVE** - флаг активности ["Y"|"N"] - **TITLE** - заголовок группы - **LID** - ID сайта - **C\_SORT** - порядок сортировки - **TIMESTAMP\_X** - время изменения записи в базе данных |  |
| arVote | Массив описывающий заданный опрос.  Индексы массива:- **ID** - ID опроса - **CHANNEL\_ID** - ID группы опроса - **C\_SORT** - порядок сортировки - **ACTIVE** - флаг активности ["Y"|"N"] - **TIMESTAMP\_X** - время изменения записи в базе данных - **DATE\_START** - время начала опроса - **DATE\_END** - время окончания опроса - **COUNTER** - количество голосований по опросу - **TITLE** - заголовок опроса - **DESCRIPTION** - описание опроса - **DESCRIPTION\_TYPE** - тип описания опроса ["html"|"text"] - **IMAGE\_ID** - ID изображения - **`EVENT1`** - идентификатор типа события - " `event1`" - **`EVENT2`** - идентификатор типа события - " `event2`" - **`EVENT3`** - дополнительный параметр типа события - " `event3`" - **UNIQUE\_TYPE** - тип уникальности посетителей: 0 - не ограничено; 1 - не голосовать дважды в одной сессии; 2 - не голосовать дважды в одной сессии либо с одним cookie; 3 - не голосовать дважды в одной сессии либо с одним cookie либо с одного IP; - **KEEP\_IP\_SEC** - количество секунд в течении которых нельзя голосовать с одного IP - **TEMPLATE** - шаблон для показа формы опроса - **RESULT\_TEMPLATE** - шаблон для показа результатов опроса - **QUESTIONS** - количество вопросов - **LAMP** - индикатор: "red" - флаг активности опроса снят либо текущая дата не попадает в интервал проведения опроса; "green" - флаг активности опроса установлен и текущая дата попадает в интервал проведения опроса. |  |
| arQuestions | Массив состоящий из массивов каждый из которых описывает один вопрос.  Индексы массива:- **ID** - ID вопроса - **ACTIVE** - флаг активности ["Y"|"N"] - **C\_SORT** - порядок сортировки - **QUESTION** - текст вопроса - **QUESTION\_TYPE** - тип текста вопроса ["html"|"text"] - **IMAGE\_ID** - ID изображения - **DIAGRAM** - флаг включения вопроса в результирующую диаграмму ["Y"|"N"] - **TEMPLATE** - шаблон для показа результатов вопроса - **TIMESTAMP\_X** - дата изменения записи в базе данных |  |
| arAnswers | Массив ответов, его индексами являются ID вопросов, а значениями - список массивов, каждый из которых описывает один ответ.  Индексы массива описывающего один ответ:- **ID** - ID ответа - **ACTIVE** - флаг активности ["Y"|"N"] - **TIMESTAMP\_X** - дата изменения записи в базе данных - **QUESTION\_ID** - ID вопроса - **C\_SORT** - порядок сортировки - **MESSAGE** - текст сообщения который будет выдан рядом с ответом в форме опроса и в качестве ответа в диаграмме опроса - **COUNTER** - количество раз когда был выбран данный ответ - **FIELD\_TYPE** - тип поля ввода: 0 - radio, 1 - checkbox, 2 - dropdown list; 3 - multiselect list, 4 - text; 5 - textarea - **FIELD\_WIDTH** - ширина поля ввода - **FIELD\_HEIGHT** - высота поля ввода - **FIELD\_PARAM** - дополнительные параметры поля ввода: стиль, класс - **COLOR** - RGB цвета элемента диаграммы (например: #FFOOCC) |  |
| arDropDown | Массив с всеми элементами типа "2" (dropdown list) одного вопроса. Индексом массива является ID вопроса, а значением - массив со следующими индексами:- **REFERENCE** - текст ответа - **REFERENCE\_ID** - ID ответа |  |
| arMultiSelect | Массив с всеми элементами типа "3" (multiselect list) одного вопроса. Индексом массива является ID вопроса, а значением - массив со следующими индексами:- **REFERENCE** - текст ответа - **REFERENCE\_ID** - ID ответа |  |
| arGroupAnswers | Массив описывающий варианты ответов для элементов ввода типа "4" (text) и "5" (textarea). Индексом массива является ID вопроса, а значением - список массивов со следующими индексами:- **MESSAGE** - текст ответа - **COUNTER** - количество таких ответов |  |
| getGroupAnswers | Флаг принимающий следующие значения: "Y" - собирать массив arGroupAnswers; "N" - собирать массив arGroupAnswers не нужно. | Удален с 12.0.0 |
| arrAddParams | Необязательный параметр. Значение по умолчанию - "N". | 12.0.0 |

### Примеры использования

```
<?
// возвращает форму заданного опроса с учётом прав пользователя
function ShowVote($VOTE_ID, $template1="")
{
	global $MESS, $VOTING_LAMP, $VOTING_OK, $USER_ALREADY_VOTE, $USER_GROUP_PERMISSION, $VOTE_USER_ID, $VOTE_PERMISSION;
	$VOTE_ID = GetVoteDataByID($VOTE_ID, $arChannel, $arVote, $arQuestions, $arAnswers, $arDropDown, $arMultiSelect, $arGroupAnswers, "N");
	if (intval($VOTE_ID)>0)
	{
		$perm = CVoteChannel::GetGroupPermission($arChannel["ID"]);
		if (intval($perm)>=2)
		{
			$template = (strlen($arVote["TEMPLATE"])<=0) ? "default.php" : $arVote["TEMPLATE"];
			$VOTE_PERMISSION = CVote::UserGroupPermission($arChannel["ID"]);
			require_once ($_SERVER["DOCUMENT_ROOT"]."/bitrix/modules/vote/include.php");
			@include_once (GetLangFileName($_SERVER["DOCUMENT_ROOT"]."/bitrix/php_interface/lang/", "/".$template));
			$path = COption::GetOptionString("vote", "VOTE_TEMPLATE_PATH", "/bitrix/php_interface/include/vote/show/");
			if (strlen($template1)>0) $template = $template1;
			@include($_SERVER["DOCUMENT_ROOT"].$path.$template);
		}
	}
}
?>Копировать
```

```
<?
// получаем данные по опросу
$VOTE_ID = GetVoteDataByID($PUBLIC_VOTE_ID, $arChannel, $arVote, $arQuestions, $arAnswers, $arDropDown, $arMultiSelect, $arGroupAnswers, "N", $template, $res_template);
$VOTE_ID = intval($VOTE_ID);
// если поступивший ID опроса корректный то
if ($VOTE_ID>0 && $arVote["LAMP"]=="green")
{
	...
}
?>Копировать
```

Новинки документации в соцсетях: