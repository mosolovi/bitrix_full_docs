[Подписка, рассылки](/api_help/subscribe/index.php)

[Классы](/api_help/subscribe/classes/index.php)

[CSubscriptionGeneral](/api_help/subscribe/classes/csubscriptiongeneral/index.php)

Update (доступен с 3.0.5)

Update
======

Включить вкладки

Описание и параметры

Возвращаемые значения

Примеры использования

### Описание и параметры

```
mixed
CSubscription::Update(
	int ID,
	array arFields,
	string SITE_ID = SITE_ID
);Копировать
```

Метод изменяет данные подписки. Если изменяется адрес подписки, то метод снимает подтверждение с подписки и
генерирует событие для отправки письма с кодом подтверждения подписки (если это явно не запрещено).
Если подписка не подтверждена, а массив полей включает в себя правильный CONFIRM\_CODE, то подписка
подтверждается. Метод нестатический.

#### Параметры

| Параметр | Описание | C версии |
| --- | --- | --- |
| ID | Идентификатор подписки. |  |
| arFields | Массив со значениями [полей объекта "Подписка"](/api_help/subscribe/classes/csubscriptiongeneral/csubscriptiongeneralfields.php). Дополнительно могут быть указаны поля:     RUB\_ID - массив идентификаторов рассылок, на которые подписывается адрес;     SEND\_CONFIRM - отправлять ли письмо с кодом подтверждения подписчику при изменениии адреса (Y/N). |  |
| SITE\_ID | Идентификатор сайта, по которому определяется шаблон письма о подтверждении подписки. По умолчанию параметр принимает значение текущего сайта. Обязателен при использовании RUB\_ID. Если ALL\_SITES указан в массиве **$arFields**, то SITE\_ID можно не указывать | 4.0.0 |

### Возвращаемые значения

В случае успешного изменения возвращается true. В противном случает возвращается false,
и переменная класса LAST\_ERROR содержит сообщение об ошибке (так же возбуждается исключение [CMain::ThrowException](/api_help/main/reference/cmain/throwexception.php)).
  
  
При успешном результате переменная класса LAST\_MESSAGE содержит строку-код информационного сообщения.
Возможные значения:  
   "CONF" - подписка подтверждена;  
   "SENT" - сгенерировано событие для отправки письма с кодом подтверждения.

### Примеры использования

```
$subscr = new CSubscription;
//confirmation code from letter or confirmation form
if($CONFIRM_CODE <> "" && $ID > 0 && empty($action))
{
	if($str_CONFIRMED <> "Y")
	{
		//subscribtion confirmation
		if($subscr->Update($ID, array("CONFIRM_CODE"=>$CONFIRM_CODE)))
			$str_CONFIRMED = "Y";
		$strWarning .= $subscr->LAST_ERROR;
		$iMsg = $subscr->LAST_MESSAGE;
	}
}
//*************************
//form actions processing
//*************************
if($ID > 0)
{
	if($action == "unsubscribe" && CSubscription::IsAuthorized($ID))
	{
		//unsubscription
		if($subscr->Update($ID, array("ACTIVE"=>"N")))
		{
			$str_ACTIVE = "N";
			$iMsg = "UNSUBSCR";
		}
	}
	if($action == "activate" && CSubscription::IsAuthorized($ID))
	{
		//activation
		if($subscr->Update($ID, array("ACTIVE"=>"Y")))
		{
			$str_ACTIVE = "Y";
			$iMsg = "ACTIVE";
		}
	}
}Копировать
```

Новинки документации в соцсетях: