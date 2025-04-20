[Подписка, рассылки](/api_help/subscribe/index.php)

[События](/api_help/subscribe/events/index.php)

BeforePostingSendMail (доступно с 6.0.1)

BeforePostingSendMail
=====================

Включить вкладки

Описание и параметры

Смотрите также

Пример функции-обработчика

### Описание и параметры

```
функция-обработчик(
	array arFields
);Копировать
```

Событие "BeforePostingSendMail" вызывается перед отправкой выпуска из метода [CPosting::SendMessage](/api_help/subscribe/classes/cpostinggeneral/cpostingsendmessage.php).

#### Параметры

| Параметр | Описание |
| --- | --- |
| **arFields** | Массив следующего содержания:  * POSTING\_ID - идентификатор выпуска. * EMAIL - адрес на который будет отправлен выпуск. * SUBJECT - заголовок письма (в кодированном виде, если установлена соответсветствующая настройка модуля). * BODY - тело письма уже отформатированное в соответствии со стандартом MIME. * HEADER - служебные заголовки. * EMAIL\_EX - расширенная информация о получателе, см. [Поля CPosting.](/api_help/subscribe/classes/cpostinggeneral/cpostingfields.php) |

Данный обработчик должен вернуть массив аналогичного содержания. Этот массив будет передан в качестве аргумента следующему обработчику. Проверка целостности результата обработчика в модуле не производится.

Если обработчик вернет не массив, то отправка письма выполняться не будет. Однако в случае возврата false письмо будет считаться не отправленным, иначе отправка будет отмечена как успешная.

### Смотрите также

* [CPosting::SendMessage](/api_help/subscribe/classes/cpostinggeneral/cpostingsendmessage.php)
* [Обработка событий](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Пример функции-обработчика

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler("subscribe", "BeforePostingSendMail", Array("MyClass", "BeforePostingSendMailHandler"));
class MyClass
{
	// создаем обработчик события "BeforePostingSendMail"
	public static function BeforePostingSendMailHandler($arFields)
	{
		$USER_NAME = "Подписчик";
		//Попробуем найти подписчика.
		$rs = CSubscription::GetByEmail($arFields["EMAIL"]);
		if($ar = $rs->Fetch())
		{
			if(intval($ar["USER_ID"]) > 0)
			{
				$rsUser = CUser::GetByID($ar["USER_ID"]);
				if($arUser = $rsUser->Fetch())
				{
					$USER_NAME = $arUser["NAME"]." ".$arUser["LAST_NAME"];
				}
			}
		}
		$arFields["BODY"] = str_replace("#NAME#", $USER_NAME, $arFields["BODY"]);
		return $arFields;
	}
}
?>Копировать
```

Новинки документации в соцсетях: