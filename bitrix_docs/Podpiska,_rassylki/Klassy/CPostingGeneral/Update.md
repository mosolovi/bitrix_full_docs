[Подписка, рассылки](/api_help/subscribe/index.php)

[Классы](/api_help/subscribe/classes/index.php)

[CPostingGeneral](/api_help/subscribe/classes/cpostinggeneral/index.php)

Update (доступен с 3.1.1)

Update
======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CPosting::Update(
	int ID,
	array arFields
);Копировать
```

Метод изменяет информацию о выпуске по его идентификатору. Метод нестатический.

#### Параметры

| Параметр | Описание | C версии |
| --- | --- | --- |
| ID | Идентификатор выпуска. |  |
| arFields | Массив со значениями [полей объекта "Выпуск"](/api_help/subscribe/classes/cpostinggeneral/cpostingfields.php). Дополнительно могут быть указаны поля:  RUB\_ID - массив идентификаторов рассылок;  GROUP\_ID - массив идентификаторов групп пользователей. |  |

#### Возвращаемые значения

В случае успешного изменения возвращается true. В противном случает возвращается false,
и переменная класса LAST\_ERROR содержит сообщение об ошибке.

### Примеры использования

```
$posting = new CPosting;
$arFields = Array(
	"FROM_FIELD" => $FROM_FIELD,
	"TO_FIELD" => $TO_FIELD,
	"BCC_FIELD" => $BCC_FIELD,
	"EMAIL_FILTER" => $EMAIL_FILTER,
	"SUBJECT" => $SUBJECT,
	"BODY_TYPE" => ($BODY_TYPE <> "html"? "text":"html"),
	"BODY" => $BODY,
	"DIRECT_SEND" => ($DIRECT_SEND <> "Y"? "N":"Y"),
	"CHARSET" => $CHARSET,
	"SUBSCR_FORMAT" => ($SUBSCR_FORMAT<>"html" && $SUBSCR_FORMAT<>"text"? false:$SUBSCR_FORMAT),
	"RUB_ID" => $RUB_ID,
	"GROUP_ID" => $GROUP_ID
);
if($STATUS <> "")
{
	if($STATUS<>"S" && $STATUS<>"E" && $STATUS<>"P")
		$STATUS = "D";
	$arFields["STATUS"] = $STATUS;
	if($STATUS == "D")
	{
		$arFields["DATE_SENT"] = false;
		$arFields["SENT_BCC"] = "";
		$arFields["ERROR_EMAIL"] = "";
	}
}
if(!$posting->Update($ID, $arFields))
	$strError = $posting->LAST_ERROR;Копировать
```

Новинки документации в соцсетях: