[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnBeforeEventAdd (с версии 6.0.2)

OnBeforeEventAdd
================

Включить вкладки

Описание и параметры

Смотрите также

Пример функции-обработчика

### Описание и параметры

```
функция-обработчик(
	string &$event,
	string &$lid,
	array &$arFields,
	string &$message_id,
	array &$files,
	string languageId = ''
)Копировать
```

Событие **OnBeforeEventAdd** вызывается в момент добавления почтового события [в таблицу b\_event](/api_help/main/general/mailevents.php). Как правило, задача обработчика данного события - изменить или добавить какое-либо значение, передаваемое в макросы почтового шаблона.

#### Параметры

| Параметр | Описание | С версии |
| --- | --- | --- |
| *$event* | Идентификатор типа почтового события, например FORM\_FILLING\_ANKETA |  |
| *$lid* | ID сайта, на котором был вызов метода CEvent::Send() |  |
| *$arFields* | Массив параметров, которые передаются в обработчик события.   Пример массива:     ``` Array 	( 		[RS_FORM_ID] => 1 		[RS_FORM_NAME] => Анкета посетителя сайта 		[RS_FORM_VARNAME] => ANKETA 		[RS_FORM_SID] => ANKETA 		[RS_RESULT_ID] => 11 		[RS_DATE_CREATE] => 24.07.2011 16:59:55 		[RS_USER_ID] => 1 		[RS_USER_EMAIL] => my@email.com 		[RS_USER_NAME] =>   		[RS_USER_AUTH] =>   		[RS_STAT_GUEST_ID] => 1 		[RS_STAT_SESSION_ID] => 1 		[VS_NAME] => sfdsf 		[VS_NAME_RAW] => sfdsf 		[VS_BIRTHDAY] => 21.07.2011 		[VS_BIRTHDAY_RAW] => 21.07.2011 		[VS_ADDRESS] => sdfdsf 		[VS_ADDRESS_RAW] => sdfdsf 		[VS_MARRIED] => Да [4] 		[VS_MARRIED_RAW] => Да 		[VS_INTEREST] => физика (2) [7] 					программирование (5) [10] 		[VS_INTEREST_RAW] => физика,программирование 		[VS_AGE] => 30-39 (30) [13] 		[VS_AGE_RAW] => 30-39 		[VS_EDUCATION] => высшее (3) [19] 		[VS_EDUCATION_RAW] => высшее 		[VS_INCOME] =>   		[VS_INCOME_RAW] =>   		[VS_PHOTO] =>   		[VS_PHOTO_RAW] =>   	)Копировать ``` |  |
| *$message\_id* | Идентификатор почтового шаблона (если указан). Если переменная определена в обработчике, то среди нескольких почтовых шаблонов по одному типу будет отправлен только с этим ID, а не все. | 11.0.16 |
| *$files* | Файл | 16.0.1 |
| *$languageId* | (По умолчанию - текущий язык) Отвечает за отправку уведомлений на указанном языке (у почтовых шаблонов параметр "Язык"). Отправляются все шаблоны без указания языка и те у которых язык соответствует $languageId. Фильтр по языку шаблонов не выполняется если передается переменная $messageId.  Пример функции-обработчика:   ``` <? class MyClass { 	function onBeforeEventAdd(&$event, &$lid, &$arFields, &$messageId, &$files, &$languageId) 	{ 		// код 	} } ?>Копировать ``` | 16.5.8 |

#### Возвращаемое значение

Нет. Начиная с версии ядра 11.0.16 при возврате *false* добавление почтового события отменяется.

### Смотрите также

* [Событие "OnBeforeEventSend"](/api_help/main/events/onbeforeeventsend.php)
* [CEvent::Send](/api_help/main/reference/cevent/send.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Пример функции-обработчика

```
<?
//Обработчик в файле /bitrix/php_interface/init.php
AddEventHandler("main", "OnBeforeEventAdd", array("MyClass", "OnBeforeEventAddHandler"));
class MyClass
{
	public static function OnBeforeEventAddHandler(&$event, &$lid, &$arFields)
	{
		$arFields["NEW_FIELD"] = "Новый макрос для почтового шаблона";
		$arFields["VS_BIRTHDAY"] = "Изменение существующего макроса";
		$lid = 's2'; //Изменяем привязку к сайту
	}
}
?>
Копировать
```

Новинки документации в соцсетях: