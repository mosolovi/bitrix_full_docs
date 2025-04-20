[Подписка, рассылки](/api_help/subscribe/index.php)

[Классы](/api_help/subscribe/classes/index.php)

[CSubscriptionGeneral](/api_help/subscribe/classes/csubscriptiongeneral/index.php)

Add (доступен с 3.0.5)

Add
===

Включить вкладки

Описание и параметры

Возвращаемые значения

Примеры использования

### Описание и параметры

```
int
CSubscription::Add(
	array arFields,
	string SITE_ID = SITE_ID
);Копировать
```

Метод добавляет подписку на рассылки и отправляет подписчику письмо с кодом подтверждения подписки (если не указано не отправлять). Метод нестатический.

#### Параметры

| Параметр | Описание | C версии |
| --- | --- | --- |
| arFields | Массив со значениями [полей объекта "Подписка"](/api_help/subscribe/classes/csubscriptiongeneral/csubscriptiongeneralfields.php). Дополнительно могут быть указаны поля:    * **RUB\_ID** - массив идентификаторов рассылок, на которые подписывается адрес; * **SEND\_CONFIRM** - отправлять ли письмо с кодом подтверждения подписчику (Y/N). * **ALL\_SITES** - отписать подписчика от рассылок всех сайтов или только от заданного SITE\_ID (Y/N). * **USER\_ID** - необязательный. Идентификатор зарегистрированного пользователя. |  |
| SITE\_ID | Идентификатор сайта, по которому определяется шаблон письма о подтверждении подписки. По умолчанию параметр принимает значение текущего сайта. | 4.0.0 |

#### Требования к полям, передаваемым в arFields

* EMAIL - должно содержать правильный адрес e-mail (см. функцию [check\_email](/api_help/main/functions/other/check_email.php)). Также выполняется проверка уникальности EMAIL.

### Возвращаемые значения

В случае успешного добавления возвращается ID подписки. В противном случает возвращается false, и переменная класса LAST\_ERROR содержит сообщение об ошибке (так же возбуждается исключение [CMain::ThrowException](/api_help/main/reference/cmain/throwexception.php)).

### Примеры использования

```
//there must be at least one newsletter category
if(!is_array($RUB_ID) || count($RUB_ID) == 0)
	$strWarning .= "There must be at least one category."."<br>";
if($strWarning == "")
{
	$arFields = Array(
		"USER_ID" => ($USER->IsAuthorized()? $USER->GetID():false),
		"FORMAT" => ($FORMAT <> "html"? "text":"html"),
		"EMAIL" => $EMAIL,
		"ACTIVE" => "Y",
		"RUB_ID" => $RUB_ID
	);
	$subscr = new CSubscription;
	//can add without authorization
	$ID = $subscr->Add($arFields);
	if($ID>0)
		CSubscription::Authorize($ID);
	else
		$strWarning .= "Error adding subscription: ".$subscr->LAST_ERROR."<br>";
}Копировать
```

Новинки документации в соцсетях: