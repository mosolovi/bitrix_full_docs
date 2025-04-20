[Открытые линии](/api_help/imopenlines/index.php)

[События](/api_help/imopenlines/events/index.php)

OnBeforeSessionTransfer

OnBeforeSessionTransfer
=======================

Включить вкладки

Описание и параметры

Проверка на корректность

Пример кода

### Описание и параметры

В событие приходит объект \Bitrix\Main\Event.

Входящие параметры можно получить через `$eventParams = $event->getParameters();`

#### Параметры

| Параметр | Описание |
| --- | --- |
| session | Массив данных сессии, которая перенаправляется на нового оператора. Текущий оператор, с которого предполагается снять диалог, указан в элементе **OPERATOR\_ID**. |
| config | Информация об открытой линии, к которой принадлежит сессия. |
| chat | Объект **Bitrix\ImOpenLines\Chat** из которого можно получить информацию о чате, который относится к сессии. |
| reasonReturn | Причина    **Перечень доступных причин:**     Внимание! Актуальный список причин можно увидеть в классе \Bitrix\ImOpenLines\Queue.  \Bitrix\ImOpenLines\Queue::REASON\_DEFAULT; //по умолчанию  \Bitrix\ImOpenLines\Queue::REASON\_OPERATOR\_ABSENT = 'VACATION'; //отпуск  \Bitrix\ImOpenLines\Queue::REASON\_OPERATOR\_DAY\_PAUSE = 'NONWORKING'; //нерабочее время  \Bitrix\ImOpenLines\Queue::REASON\_OPERATOR\_DAY\_END = 'NONWORKING'; //нерабочее время  \Bitrix\ImOpenLines\Queue::REASON\_OPERATOR\_DELETED = 'DISMISSAL'; //оператор уволен  \Bitrix\ImOpenLines\Queue::REASON\_REMOVED\_FROM\_QUEUE = 'REMOVING'; //оператор удален  \Bitrix\ImOpenLines\Queue::REASON\_OPERATOR\_NOT\_AVAILABLE = 'NOT\_AVAILABLE'; //оператор недоступен  \Bitrix\ImOpenLines\Queue::REASON\_OPERATOR\_OFFLINE = 'OFFLINE'; //оператор не в сети  \Bitrix\ImOpenLines\Queue::REASON\_QUEUE\_TYPE\_CHANGED = 'DEFAULT'; //по умолчанию того, почему происходит назначение нового оператора. |
| newOperatorQueue | Массив. Самый важный параметр, который и необходимо вернуть в событии. При необходимости в элементы массива можно вносить изменения и изменять штатную логику.    Элементы массива:  * RESULT - True или false. Тип bool. Указывает, удалось ли найти оператора/ов для назначения (даже если найден тот же самый, что и сейчас, оператор). * OPERATOR\_ID - Идентификатор оператора, на которого назначается диалог. Тип int. Если передано значение, означает, что это режим работы очереди не "одновременно всем". Можно указать id линии, предварив префиксом queue. Например "queue55" для переадресации на линию с id 55. * OPERATOR\_LIST - Список операторов, на которых будет направлен диалог. Тип array. Если передано значение, то работает назначение сразу на нескольких операторов. Т.е. у сессии нет ответственных, но диалог показывается сразу нескольким. **Не использовать одновременно с OPERATOR\_ID!** Направленный диалог не будет автоматически принят, оператор должен будет еще принять диалог. * DATE\_QUEUE - Дата следующей попытки распределения диалога. Должен быть передан либо объект Bitrix\Main\Type\DateTime, либо false. Если передается false, то обязательно должно быть указано 'OPERATOR\_ID' или 'OPERATOR\_LIST'. * QUEUE\_HISTORY - История назначения по очереди. Нужно добавить в него добавляемого оператора (если его там нет) в конец в формате: ключ массива - id пользователя. Значение: true. |

### Проверка на корректность

  

Внимательно проверяется корректность данных, которые возвращает обработчик. Если что-то не пройдет проверку, то отработает штатный алгоритм, как будто бы обработчика и нет.

Было создано дополнительное событие *OnErrorEventBeforeSessionTransfer*.

На него можно подписать на время отладки. В параметрах передается массив ошибок и объект, который вернул обработчик события.

  

### Пример результата

```
array (
	'errors' => 
	array (
		0 => 'The result of the processing of the event returned with an error',
	),
	'eventResult' => 
	Bitrix\Main\EventResult::__set_state(array(
		'moduleId' => NULL,
		'handler' => NULL,
		'type' => 0,
		'parameters' => 
		array (
			'RESULT' => 5,
		),
	)),
)Копировать
```

Данное решение должно существенно облегчить дебаг.

### Пример кода

  

### "Болванка" событий

```
$eventManager = \Bitrix\Main\EventManager::getInstance();
$eventManager->addEventHandler('imopenlines', 'OnBeforeSessionTransfer', 'onBeforeSessionTransfer');
$eventManager->addEventHandler('imopenlines', 'OnErrorEventBeforeSessionTransfer', 'onErrorEventBeforeSessionTransfer');
public static function onBeforeSessionTransfer(\Bitrix\Main\Event $event)
{
	$eventParams = $event->getParameters();
	//test
	define("LOG_FILENAME", $_SERVER["DOCUMENT_ROOT"]."/log.txt");
	AddMessage2Log(var_export($eventParams,1), 'onBeforeSessionTransfer');
	//END test
	$eventParams['newOperatorQueue'] = [
		'RESULT' => true,
		'OPERATOR_ID' => 1,
		'OPERATOR_LIST' =>
			[],
		'DATE_QUEUE' => false,
		'QUEUE_HISTORY' =>
			[
				1 => true,
			],
	];
	return new \Bitrix\Main\EventResult(
		\Bitrix\Main\EventResult::SUCCESS,
		$eventParams
	);
}
public static function onErrorEventBeforeSessionTransfer(\Bitrix\Main\Event $event)
{
	$eventParams = $event->getParameters();
	//test
	define("LOG_FILENAME", $_SERVER["DOCUMENT_ROOT"]."/log.txt");
	AddMessage2Log(var_export($eventParams,1), 'OnErrorEventBeforeSessionTransfer');
	//END test
}Копировать
```

Новинки документации в соцсетях: