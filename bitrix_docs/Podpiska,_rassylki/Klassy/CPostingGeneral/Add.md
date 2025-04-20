[Подписка, рассылки](/api_help/subscribe/index.php)

[Классы](/api_help/subscribe/classes/index.php)

[CPostingGeneral](/api_help/subscribe/classes/cpostinggeneral/index.php)

Add (доступен с 3.1.1)

Add
===

Включить вкладки

Описание и параметры

Возвращаемые значения

Примеры использования

### Описание и параметры

```
int
CPosting::Add(
	array arFields
);Копировать
```

Метод добавляет выпуск. Метод нестатический.

#### Параметры

| Параметр | Описание | С версии |
| --- | --- | --- |
| arFields | Массив со значениями [полей объекта "Выпуск"](/api_help/subscribe/classes/cpostinggeneral/cpostingfields.php)  Дополнительно могут быть указаны поля:  RUB\_ID - массив идентификаторов рассылок;  GROUP\_ID - массив идентификаторов групп пользователей. |  |

#### Требования к полям передаваемым в arFields

* FROM\_FIELD - должно содержать правильный адрес e-mail (см. функцию [check\_email](/api_help/main/functions/other/check_email.php)).
* TO\_FIELD - в случае когда поле DIRECT\_SEND равно Y не должно быть пустым.
* SUBJECT - не должно быть пустым.
* BODY - не должно быть пустым.
* AUTO\_SEND\_TIME - если задано, то должно содержать или false или дату включающую время (см. метод [CDatabase::IsDate](/api_help/main/reference/cdatabase/isdate.php))

### Возвращаемые значения

В случае успешного добавления возвращается ID выпуска. В противном случает возвращается false,
и переменная класса LAST\_ERROR содержит сообщение об ошибке (так же возбуждается исключение [CMain::ThrowException](/api_help/main/reference/cmain/throwexception.php)).

При указании статуса в поле **STATUS** следует учитывать, что при переводе из одного статуса в другой могут выполняться определенные действия. Так, например, при переводе из статуса "Черновик" ("D") в статус "В процессе" ("P") формируется список адресов, по которым будет происходить отправка. А именно, адреса, на которые требуется отправить выпуск, попадают в таблицу **b\_posting\_email** со статусом "Y". Если при добавлении выпуска сразу указать статус "В процессе" ("Р"), то процесс добавления адресов в таблицу **b\_posting\_email** не произойдет, и выпуск никому не отправится. При этом статус выпуска сменится на "S" (отправлен успешно). Выпуски хранятся в таблице **b\_posting**.

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
	"SUBSCR_FORMAT" => ($SUBSCR_FORMAT<>"html" && $SUBSCR_FORMAT<>"text"?
		false:$SUBSCR_FORMAT),
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
$ID = $posting->Add($arFields);
if($ID == false)
	echo $posting->LAST_ERROR;Копировать
```

```
// Полностью схема генерации выпуска из скрипта выглядит так:
$cPosting = new CPosting;
$ID = $cPosting->Add($arFields);
if($ID)
{
	$cPosting->ChangeStatus($ID, "P");
	$cPosting->AutoSend($ID);
}Копировать
```

Новинки документации в соцсетях: