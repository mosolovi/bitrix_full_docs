[Веб-формы](/api_help/form/index.php)

[События](/api_help/form/events/index.php)

onAfterResultUpdate (6.5.2)

onAfterResultUpdate
===================

Включить вкладки

Описание и параметры

Пример функции-обработчика

### Описание и параметры

```
функция-обработчик(
	int WEB_FORM_ID,
	int RESULT_ID,
	string(1) CHECK_RIGHTS
);Копировать
```

Обработчики события вызываются после сохранения изменений результата веб-формы. Может быть использовано для совершения каких-либо дополнительных операций с результатом веб-формы, например, для рассылки дополнительных уведомлений посредством электронной почты. Возврат обработчиком каких-либо значений не предполагается. Для изменения полей результата веб-формы стоит использовать CFormResult::SetField().

#### Параметры

| Параметр | Описание |
| --- | --- |
| *WEB\_FORM\_ID* | ID веб-формы. |
| *RESULT\_ID* | ID результата. |
| *CHECK\_RIGHTS* | Флаг "Проверять права" (Y|N). |

#### Смотрите также

* [Событие "onBeforeResultUpdate"](/api_help/form/events/onbeforeresultupdate.php)
* [Событие "onAfterResultAdd"](/api_help/form/events/onafterresultadd.php)

### Пример функции-обработчика

```
public static function my_onAfterResultAddUpdate($WEB_FORM_ID, $RESULT_ID)
{
	// действие обработчика распространяется только на форму с ID=6
	if ($WEB_FORM_ID == 6) 
	{
		// запишем в дополнительное поле 'user_ip' IP-адрес пользователя
		CFormResult::SetField($RESULT_ID, 'user_ip', $_SERVER["REMOTE_ADDR"]);
	}
}
// зарегистрируем функцию как обработчик двух событий
AddEventHandler('form', 'onAfterResultAdd', 'my_onAfterResultAddUpdate');
AddEventHandler('form', 'onAfterResultUpdate', 'my_onAfterResultAddUpdate');Копировать
```

Новинки документации в соцсетях: