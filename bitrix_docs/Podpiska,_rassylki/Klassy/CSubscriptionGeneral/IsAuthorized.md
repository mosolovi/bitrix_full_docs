[Подписка, рассылки](/api_help/subscribe/index.php)

[Классы](/api_help/subscribe/classes/index.php)

[CSubscriptionGeneral](/api_help/subscribe/classes/csubscriptiongeneral/index.php)

IsAuthorized (доступен с 3.3.2)

IsAuthorized
============

```
bool
CSubscription::IsAuthorized(
	int ID
);Копировать
```

Метод проверяет, авторизован ли текущий посетитель для доступа к информации о подписке. Метод статический.

#### Параметры

| Параметр | Описание | C версии |
| --- | --- | --- |
| ID | Идентификатор подписки. |  |

#### Возвращаемые значения

Если посетитель авторизован для доступа к данной подписке, то возвращается true, иначе false.

#### Пример использования

```
//check whether already authorized to show password field
$bShowPass = true;
$aSubscr = CSubscription::GetUserSubscription();
if($aSubscr["ID"] > 0)
{
	//try to authorize user account's subscription
	if($aSubscr["USER_ID"]>0 && !CSubscription::IsAuthorized($aSubscr["ID"]))
		CSubscription::Authorize($aSubscr["ID"], "");
	//check authorization
	if(CSubscription::IsAuthorized($aSubscr["ID"]))
		$bShowPass = false;
}Копировать
```

Новинки документации в соцсетях: