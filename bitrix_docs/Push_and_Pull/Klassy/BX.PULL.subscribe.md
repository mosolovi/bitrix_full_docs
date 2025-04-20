[Push and Pull](/api_help/push_pull/index.php)

[Классы](/api_help/push_pull/classes/index.php)

BX.PULL.subscribe

BX.PULL.subscribe
=================

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

BX.PULL.subscribe - JS метод.

Подписка на события модуля Push&Pull. Для подписки есть [три формата](https://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=12173&LESSON_PATH=3913.4776.5413.12173), вы можете выбрать для себя подходящий в зависимости от ваших задач.

#### Параметры

| Параметр | Описание |
| --- | --- |
| type | Тип подписки ( Server, Client, Online    Здесь имеется ввиду константы:  BX.PullClient.SubscriptionType.Server,  BX.PullClient.SubscriptionType.Client,   BX.PullClient.SubscriptionType.Online ) - можно не указывать, по умолчанию будет тип Server. |
| moduleId | Модуль отправивший команду. |
| command | Команда на которую осуществляется подписка |
| callback | Функция обработчик |

### Примеры использования

Подписка на все события модуля.

```
BX.PULL.subscribe({
	moduleId: 'exampleModule',
	callback: function (data) {
		if (command == 'exampleCommandOne')   {
			doSomething();
		}
		else if (command == 'exampleCommandTwo')
		{
			doSomething2();
		}
	}.bind(this)
});Копировать
```

Подписка на одну команду

```
BX.PULL.subscribe({
	type: BX.PullClient.SubscriptionType.Server,
	moduleId: 'im',
	command: 'messageChat',
	callback: function (params, extra, command) {
		console.warn('Receive message:', params.message.text)
	}.bind(this)
});Копировать
```

Подписка на множество команд с помощью функции маршрутизатора

```
BX.PULL.subscribe({
	type: BX.PullClient.SubscriptionType.Server,
	moduleId: 'im',
	callback: function (data) {
		if (data.command == 'messageAdd')
		{
			this.doSomething();
		}
	}.bind(this)
});Копировать
```

Подписка с помощью класса маршрутизации

```
BX.PULL.subscribe(new CommandHandler(options));Копировать
```

Новинки документации в соцсетях:

© «Битрикс», 2001-2025, «1С-Битрикс», 2025

Наверх