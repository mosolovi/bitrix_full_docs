[Подписка, рассылки](/api_help/subscribe/index.php)

[Классы](/api_help/subscribe/classes/index.php)

[CSubscriptionGeneral](/api_help/subscribe/classes/csubscriptiongeneral/index.php)

Delete (доступен с 3.0.5)

Delete
======

```
mixed
CSubscription::Delete(
	int ID
);Копировать
```

Метод удаляет подписку. Метод статический.

**Примечание**. Метод использует внутреннюю транзакцию. Если у вас используется **MySQL** и **InnoDB**, и ранее была открыта транзакция, то ее необходимо закрыть до подключения метода.

#### Параметры

| Параметр | Описание | C версии |
| --- | --- | --- |
| ID | Идентификатор подписки. |  |

#### Возвращаемые значения

В случае успешного удаления возвращается результат типа [CDBResult](/api_help/main/reference/cdbresult/index.php). В противном случае возвращается false.

#### Пример использования

```
if (($res = CSubscription::Delete($ID)) &&
	$res->AffectedRowsCount() < 1 ||
	$res == false)
	echo "Error deleting subscription.";
else
	echo "Subscription deleted.";Копировать
```

Новинки документации в соцсетях: