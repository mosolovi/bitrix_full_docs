[Подписка, рассылки](/api_help/subscribe/index.php)

[Классы](/api_help/subscribe/classes/index.php)

[CSubscriptionGeneral](/api_help/subscribe/classes/csubscriptiongeneral/index.php)

ConfirmEvent (доступен с 3.0.5)

ConfirmEvent
============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CSubscription::ConfirmEvent(
	int ID,
	string SITE_ID = SITE_ID
);Копировать
```

Метод добавляет событие SUBSCRIBE\_CONFIRM для отправки подписчику письма с кодом подтверждения подписки.
Письмо формируется по шаблону типа "SUBSCRIBE\_CONFIRM - Подтверждение подписки". Метод статический.

#### Параметры

| Параметр | Описание | C версии |
| --- | --- | --- |
| ID | Идентификатор подписки. |  |
| SITE\_ID | Идентификатор сайта, по которому определяется шаблон письма о подтверждении подписки. По умолчанию параметр принимает значение текущего сайта. |  |

#### Возвращаемые значения

При успешном добавлении события возвращается true, иначе false.

Так же false возвращается если подписка уже подтверждена (CONFIRMED равно Y).

### Примеры использования

```
if($ID > 0)
{
	//confirmation code request
	if($action == "sendcode")
	{
		if(CSubscription::ConfirmEvent($ID))
			echo "Subscription confirmation was sent successfully";
	}
}Копировать
```

Новинки документации в соцсетях: