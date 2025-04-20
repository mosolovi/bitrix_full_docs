[Веб-формы](/api_help/form/index.php)

[События](/api_help/form/events/index.php)

onAfterResultStatusChange (6.5.2)

onAfterResultStatusChange
=========================

Включить вкладки

Описание и параметры

Пример функции-обработчика

### Описание и параметры

```
функция-обработчик(
	int WEB_FORM_ID,
	int RESULT_ID,
	int NEW_STATUS_ID,
	string(1) CHECK_RIGHTS
);Копировать
```

Обработчики события вызываются после изменения статуса результата веб-формы. Может быть использовано, например, для каких-либо дополнительных уведомлений посредством электронной почты, а также, как замена обработчика статуса веб-формы. Возврат обработчиком каких-либо значений не предполагается. Для изменения полей результата веб-формы стоит использовать CFormResult::SetField().

#### Параметры

| Параметр | Описание |
| --- | --- |
| *WEB\_FORM\_ID* | ID веб-формы. |
| *RESULT\_ID* | ID результата. |
| *NEW\_STATUS\_ID* | ID статуса. |
| *CHECK\_RIGHTS* | Флаг "Проверять права" (Y|N). |

#### Смотрите также

* [Событие "onBeforeResultStatusChange"](/api_help/form/events/onbeforeresultstatuschange.php)

### Пример функции-обработчика

```
public static function my_onAfterResultStatusChange($WEB_FORM_ID, $RESULT_ID, $NEW_STATUS_ID, $CHECK_RIGHTS)
{
	global $USER;
  
	// действие обработчика распространяется только на форму с ID=6
	if ($WEB_FORM_ID == 6) 
	{
		// 1 - статус "в проверке" (по умолчанию), 2 - статус "принято"
		// запишем в скрытое поле 'status_user' идентификатор пользователя, 
		// совершившего изменение статуса.
		if ($NEW_STATUS_ID == 2)
			CFormResult::SetField($RESULT_ID, 'status_user', $USER->ID);
	}
}
// зарегистрируем функцию как обработчик события
AddEventHandler('form', 'onAfterResultStatusChange', 'my_onAfterResultStatusChange');Копировать
```

Новинки документации в соцсетях: