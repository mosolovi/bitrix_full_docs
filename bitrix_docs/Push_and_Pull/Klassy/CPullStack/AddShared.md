[Push and Pull](/api_help/push_pull/index.php)

[Классы](/api_help/push_pull/classes/index.php)

[CPullStack](/api_help/push_pull/classes/cpullstack/index.php)

AddShared (12.5.5)

AddShared
=========

```
CPullStack::AddShared(
	Array(
		'module_id' => 'test',
		'command' => 'check',
		'params' => Array(),
	)
);Копировать
```

Метод производит отправку данных всем пользователям (в общий канал **Сервера очередей**). Метод статический.

**Параметры**

| Параметр | Описание | С версии |
| --- | --- | --- |
| module\_id | Модуль который отправляет команду |  |
| command | Команда которая будет обработана в JS |  |
| params | Любой набор данных, который будет обработан в JS |  |

**Примечания**:

* Вызов этого метода в конфигурации без сервера очередей не приведет к отправке сообщений, так как общий канал есть только у сервера очередей.
* **ОСОБОЕ ВНИМАНИЕ**: данный метод отправляет данные всем пользователям, передавать там секретные данные нельзя: их увидят все.

Новинки документации в соцсетях: