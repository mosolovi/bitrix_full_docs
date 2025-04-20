[Push and Pull](/api_help/push_pull/index.php)

[Классы](/api_help/push_pull/classes/index.php)

[CPullWatch](/api_help/push_pull/classes/cpullwatch/index.php)

AddToStack (11.5.0)

AddToStack
==========

```
CPullWatch::AddToStack(
	$tag, Array(
		'module_id' => 'test',
		'command' => 'check',
		'params' => Array(),
	)
);Копировать
```

Метод отправляет данные подписанным пользователям. Метод статический.

#### Параметры

| Параметр | Описание | С версии |
| --- | --- | --- |
| tag | Идентификатор подписки |  |
| module\_id | Модуль который отправляет команду |  |
| command | Команда которая будет обработана в JS |  |
| params | Любой набор данных, который будет обработан в JS |  |

Новинки документации в соцсетях: