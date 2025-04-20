[Подписка, рассылки](/api_help/subscribe/index.php)

[Классы](/api_help/subscribe/classes/index.php)

[CSubscriptionGeneral](/api_help/subscribe/classes/csubscriptiongeneral/index.php)

GetByID (доступен с 3.0.5)

GetByID
=======

```
CDBResult
CSubscription::GetByID(
	int ID
);Копировать
```

Метод выбирает подписку по ее идентификатору. Метод статический.

#### Параметры

| Параметр | Описание | С версии |
| --- | --- | --- |
| ID | Идентификатор подписки. |  |

#### Возвращаемые значения

Возвращается результат запроса типа [CDBResult](/api_help/main/reference/cdbresult/index.php). При выборке из результата методами класса CDBResult
становятся доступны [поля объекта "Подписка"](/api_help/subscribe/classes/csubscriptiongeneral/csubscriptiongeneralfields.php).

#### Пример использования

```
//new or existing subscription?
//ID==0 indicates new subscription
if(strlen($sf_EMAIL) > 0 || $ID > 0)
{
	if($ID > 0)
		$subscription = CSubscription::GetByID($ID);
	else
		$subscription = CSubscription::GetByEmail($sf_EMAIL);
	if($subscription->ExtractFields("str_"))
		$ID = (integer)$str_ID;
	else
		$ID=0;
}
else
	$ID = 0;Копировать
```

Новинки документации в соцсетях: