[Push and Pull](/api_help/push_pull/index.php)

[Классы](/api_help/push_pull/classes/index.php)

[CPullStack](/api_help/push_pull/classes/cpullstack/index.php)

AddByUser (11.5.0)

AddByUser
=========

```
CPullStack::AddByUser(
	$recipientId, Array(
		'module_id' => 'test',
		'command' => 'check',
		'params' => Array(),
	)
);Копировать
```

Метод отправляет сообщения определенному пользователю. Метод статический.

**Параметры**

| Параметр | Описание | С версии |
| --- | --- | --- |
| recipientId | Получатель сообщения |  |
| module\_id | Модуль который отправляет команду |  |
| command | Команда которая будет обработана в JS |  |
| params | Любой набор данных, который будет обработан в JS |  |

Если нужно отправить команду множеству получателей, то приходится выполнять метод в цикле. В таких случаях лучше использовать [CPullStack::AddByUsers](/api_help/push_pull/classes/cpullstack/addbyusers.php) в которой первый параметр - массив пользователей.

Новинки документации в соцсетях: