[Веб-мессенджер](/api_help/im/index.php)

[События](/api_help/im/events/index.php)

OnBeforeMessageNotifyAdd (с версии 12.1.3)

OnBeforeMessageNotifyAdd
========================

Включить вкладки

Описание

Примеры использования

### Описание

Событие применяется для работы с сообщениями Веб-мессенджера. Для этого необходимо добавить обработчик события на модуль **im**.

Можно отменять отправку сообщения, например. Для этого нужно вернуть либо *false*, либо массив `Array('result' => false, 'reason' => 'причина отмены')` тогда в мессенджере этот текст будет указан в интерфейсе чата. В тексте доступен ограниченный html - a, b, i, u, br.

### Примеры использования

```
AddEventHandler("im", "OnBeforeMessageNotifyAdd", "___OnBeforeMessageNotifyAdd");
public static function ___OnBeforeMessageNotifyAdd($arFields)
{
	global $USER;
	if(!$USER->IsAdmin() && $arFields['MESSAGE_TYPE'] == 'P')
	{
		$imMaxMessagePerDay = 10;
		$date = date('Ymd');
		$_SESSION['IM_ANTI_SPAM'][$date]++;
		if ($_SESSION['IM_ANTI_SPAM'][$date] > $imMaxMessagePerDay)
		{
			return Array(
				'reason' => 'Вы не можете отправлять более 10 сообщений в день',
				'result' => false,
			);
		}
	}
}Копировать
```

Результат:

![](/upload/api_help/main/OnBeforeMessageNotifyAdd.png)

Новинки документации в соцсетях: