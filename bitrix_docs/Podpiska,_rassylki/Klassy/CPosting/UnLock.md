[Подписка, рассылки](/api_help/subscribe/index.php)

[Классы](/api_help/subscribe/classes/index.php)

[CPosting](/api_help/subscribe/classes/cposting/index.php)

UnLock (доступен с 4.0.7)

UnLock
======

```
bool
CPosting::UnLock(
	int ID
);Копировать
```

Метод возвращает true при успешном снятии блокировки выпуска и false при неуспешном. Используется при отправке выпусков. Метод статический.

#### Параметры

| Параметр | Описание | C версии |
| --- | --- | --- |
| ID | Идентификатор выпуска. |  |

#### Возвращаемые значения

В случае успешного снятия блокировки возвращается true. В противном случае возвращается false.

#### Пример использования

```
CPosting::UnLock($ID);Копировать
```

Новинки документации в соцсетях: