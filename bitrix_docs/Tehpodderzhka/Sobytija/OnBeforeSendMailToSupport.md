[Техподдержка](/api_help/support/index.php)

[События](/api_help/support/support_events/index.php)

OnBeforeSendMailToSupport (7.0.0)

OnBeforeSendMailToSupport
=========================

Включить вкладки

Описание и параметры

Смотрите также

Пример функции-обработчика

### Описание и параметры

```
функция-обработчик(
	array $arFields,
	bool $is_new
)Копировать
```

Событие "OnBeforeSendMailToSupport" вызывается непосредственно перед отправкой письма сотруднику модуля "Тех. поддержка". Как правило задачи обработчика данного события - выполнить ту или иную операцию, перед отправкой письма.

#### Параметры

| Параметр | Описание |
| --- | --- |
| $arFields | В массиве находятся параметры события, переданные в обработчик события. Пример массива:     ``` Array ( 	[ID] => 1 	[LANGUAGE] => ru 	[LANGUAGE_ID] => ru 	[WHAT_CHANGE] => < добавлено сообщение > 	[DATE_CREATE] => 24.07.2011 19:22:38 	[TIMESTAMP] => 24.07.2011 20:19:57 	[DATE_CLOSE] =>  	[TITLE] => Моё первое сообщение 	[STATUS] => В стадии решения 	[DIFFICULTY] => Средний 	[CATEGORY] => Общие вопросы 	[CRITICALITY] => Высокая 	[RATE] =>  	[SLA] => По умолчанию 	[SOURCE] =>  	[MESSAGES_AMOUNT] => 10 	[SPAM_MARK] =>  	[ADMIN_EDIT_URL] => /bitrix/admin/ticket_edit.php 	[PUBLIC_EDIT_URL] => /communication/support/ 	[OWNER_EMAIL] => mifd@dfdf.ru 	[OWNER_USER_ID] => 2 	[OWNER_USER_NAME] => Василий Петров 	[OWNER_USER_LOGIN] => bx_test 	[OWNER_USER_EMAIL] => mifd@dfdf.ru 	[OWNER_TEXT] => [2] (bx_test) Василий Петров 	[OWNER_SID] =>  	[SUPPORT_EMAIL] => my@email.com 	[RESPONSIBLE_USER_ID] =>  	[RESPONSIBLE_USER_NAME] =>   	[RESPONSIBLE_USER_LOGIN] =>  	[RESPONSIBLE_USER_EMAIL] =>  	[RESPONSIBLE_TEXT] =>  	[SUPPORT_ADMIN_EMAIL] =>  	[CREATED_USER_ID] => 2 	[CREATED_USER_LOGIN] => bx_test 	[CREATED_USER_EMAIL] => mifd@dfdf.ru 	[CREATED_USER_NAME] => Василий Петров 	[CREATED_MODULE_NAME] =>  	[CREATED_TEXT] => [2] (bx_test) Василий Петров 	[MODIFIED_USER_ID] => 2 	[MODIFIED_USER_LOGIN] => bx_test 	[MODIFIED_USER_EMAIL] => mifd@dfdf.ru 	[MODIFIED_USER_NAME] => Василий Петров 	[MODIFIED_MODULE_NAME] =>  	[MODIFIED_TEXT] => [2] (bx_test) Василий Петров 	[MESSAGE_AUTHOR_USER_ID] => 2 	[MESSAGE_AUTHOR_USER_NAME] => Василий Петров 	[MESSAGE_AUTHOR_USER_LOGIN] => bx_test 	[MESSAGE_AUTHOR_USER_EMAIL] => mifd@dfdf.ru 	[MESSAGE_AUTHOR_TEXT] => [2] (bx_test) Василий Петров 	[MESSAGE_AUTHOR_SID] =>  	[MESSAGE_SOURCE] =>  	[MESSAGE_HEADER] => ======================= СООБЩЕНИЕ ================================== 	[MESSAGE_BODY] =>  Ваше обращение успешно решили. 	[MESSAGE_FOOTER] => ==================================================================== 	[FILES_LINKS] =>  	[IMAGE_LINK] =>  	[SUPPORT_COMMENTS] =>  )Копировать ``` |
| $is\_new | Содержит true в случае если это сообщение первое в обращении, иначе возвращается false |

#### Возвращаемое значение

Возвращает набор полей письма

### Смотрите также

* [OnBeforeSendMailToAuthor](/api_help/support/support_events/onbeforesendmailtoauthor.php)

### Пример функции-обработчика

```
<?
//Обработчик в файле /bitrix/php_interface/init.php
//Дублируем письмо в сообщение соц. сети
AddEventHandler("support", "OnBeforeSendMailToSupport", array("MyClass", "OnBeforeSendMailToSupportHandler"));
class MyClass
{
	public static function OnBeforeSendMailToSupportHandler($arFields, $is_new)
	{
		if (CModule::IncludeModule("socialnetwork"))
		{
			$servername = "site.ru";
			$message = "";
			$message .= "Тема: ".$arFields["TITLE"]."[".$arFields["ID"]."] (Изменения в обращении)\r\n";
			$message .= $arFields["WHAT_CHANGE"]."\r\n";
			$message .= "От кого: ".$arFields["MESSAGE_SOURCE"]." ".$arFields["MESSAGE_AUTHOR_SID"]." ".$arFields["MESSAGE_AUTHOR_TEXT"]."\r\n";
			$message .= $arFields["MESSAGE_HEADER"];
			$message .= $arFields["MESSAGE_BODY"];
			$message .= $arFields["MESSAGE_FOOTER"]."\r\n";
			$message .= "Для просмотра и редактирования обращения воспользуйтесь ссылкой:\r\n";
			$message .= "http://".$servername.$arFields["ADMIN_EDIT_URL"]."?ID=".$arFields["ID"]."\r\n";
			
			$arPamams = array( 
				"FROM_USER_ID" => 1, 
				"TO_USER_ID" => 1, 
				"MESSAGE" => $message, 
				"=DATE_CREATE" => $GLOBALS["DB"]->CurrentTimeFunction(), 
				"MESSAGE_TYPE" => "P", 
			); 
			CSocNetMessages::Add($arPamams);
		}
	}
}
?>Копировать
```

Новинки документации в соцсетях: