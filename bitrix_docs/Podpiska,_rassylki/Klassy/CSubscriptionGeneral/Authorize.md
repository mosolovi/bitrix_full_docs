[Подписка, рассылки](/api_help/subscribe/index.php)

[Классы](/api_help/subscribe/classes/index.php)

[CSubscriptionGeneral](/api_help/subscribe/classes/csubscriptiongeneral/index.php)

Authorize (доступен с 3.3.2)

Authorize
=========

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CSubscription::Authorize(
	int ID,
	string CONFIRM_CODE = false
);Копировать
```

Авторизует посетителя для доступа к редактированию подписки.
Признак успешной авторизации сохраняется в PHP-сессии ($\_SESSION["SESS\_SUBSCR\_AUTH"][$ID]).

Если подписка анонимная, то авторизация проверяется по
коду подтверждения подписки. Если подписка принадлежит зарегистрированному пользователю, то доступ предоставляется
только авторизованному пользователю-владельцу подписки. Метод статический.

#### Параметры

| Параметр | Описание | C версии |
| --- | --- | --- |
| ID | Идентификатор подписки. |  |
| CONFIRM\_CODE | Пароль для авторизации доступа, должен совпадать с кодом подтверждения подписки, сгенерированным при добавлении или изменении адреса подписки. Если параметр принимает значение false, то производится безусловная авторизация. |  |

#### Возвращаемые значения

При успешной авторизации доступа к подписке возвращается true, иначе false.

### Примеры использования

```
//try to authorize subscription by CONFIRM_CODE or user password AUTH_PASS
if($ID > 0 && !CSubscription::IsAuthorized($ID))
{
	if($str_USER_ID > 0 && !empty($AUTH_PASS))
	{
		//trying to login user
		$usr = CUser::GetByID($str_USER_ID);
		if(($usr_arr = $usr->Fetch()))
		{
			$res = $USER->Login($usr_arr["LOGIN"], $AUTH_PASS);
			if($res["TYPE"] == "ERROR")
				$strWarning .= $res["MESSAGE"];
		}
	}
	CSubscription::Authorize($ID, (empty($AUTH_PASS)? $CONFIRM_CODE:$AUTH_PASS));
}Копировать
```

Новинки документации в соцсетях: