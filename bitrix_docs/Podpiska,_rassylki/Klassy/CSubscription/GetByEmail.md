[Подписка, рассылки](/api_help/subscribe/index.php)

[Классы](/api_help/subscribe/classes/index.php)

[CSubscription](/api_help/subscribe/classes/csubscription/index.php)

GetByEmail (доступен с 3.2.0)

GetByEmail
==========

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
CDBResult
CSubscription::GetByEmail(
	string email
);Копировать
```

Метод выбирает подписку по уникальному Email. Метод статический.

#### Параметры

| Параметр | Описание | C версии |
| --- | --- | --- |
| email | Уникальный Email подписчика. |  |

#### Возвращаемые значения

Возвращается результат запроса типа [CDBResult](/api_help/main/reference/cdbresult/index.php). При выборке из результата методами класса CDBResult
становятся доступны [поля объекта "Подписка"](/api_help/subscribe/classes/csubscriptiongeneral/csubscriptiongeneralfields.php).

### Примеры использования

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