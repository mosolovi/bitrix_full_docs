[Веб-формы](/api_help/form/index.php)

[События](/api_help/form/events/index.php)

onBeforeResultStatusChange (6.5.2)

onBeforeResultStatusChange
==========================

Включить вкладки

Описание и параметры

Пример функции-обработчика

### Описание и параметры

```
функция-обработчик(
	int WEB_FORM_ID,
	int RESULT_ID,
	int &NEW_STATUS_ID,
	string(1) CHECK_RIGHTS
);Копировать
```

Обработчики события вызываются перед изменением статуса результата веб-формы. Может быть использовано для каких-либо дополнительных проверок или даже для изменения нового статуса, а также, как замена обработчика статуса веб-формы. Возврат обработчиком каких-либо значений не предполагается. Ошибки можно возвращать посредством $APPLICATION->ThrowException().

#### Параметры

| Параметр | Описание |
| --- | --- |
| *WEB\_FORM\_ID* | ID веб-формы. |
| *RESULT\_ID* | ID результата. |
| *NEW\_STATUS\_ID* | ID статуса. |
| *CHECK\_RIGHTS* | Флаг "Проверять права" (Y|N). |

#### Смотрите также

* [Событие "onAfterResultStatusChange"](/api_help/form/events/onafterresultstatuschange.php)

### Пример функции-обработчика

```
public static function my_onBeforeResultStatusChange($WEB_FORM_ID, $RESULT_ID, $NEW_STATUS_ID, $CHECK_RIGHTS)
{
	global $USER;
  
	// действие обработчика распространяется только на форму с ID=6
	if ($WEB_FORM_ID == 6) 
	{
		// 1 - статус "в проверке" (по умолчанию), 2 - статус "принято"
		// результатам, присланным пользователем с правами администратора 
		// автоматически присвоим статус "принято".
		if ($USER->IsAdmin() && $NEW_STATUS_ID == 1)
			$NEW_STATUS_ID = 2;
	}
}
// зарегистрируем функцию как обработчик события
AddEventHandler('form', 'onBeforeResultStatusChange', 'my_onBeforeResultStatusChange');Копировать
```

Новинки документации в соцсетях: