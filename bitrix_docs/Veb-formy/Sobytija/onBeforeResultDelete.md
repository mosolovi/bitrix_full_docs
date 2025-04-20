[Веб-формы](/api_help/form/index.php)

[События](/api_help/form/events/index.php)

onBeforeResultDelete (6.5.2)

onBeforeResultDelete
====================

```
функция-обработчик(
	int WEB_FORM_ID,
	int RESULT_ID,
	string(1) CHECK_RIGHTS
);Копировать
```

Обработчики события вызываются перед удалением результата веб-формы. Может быть использовано, например, для рассылки дополнительных уведомлений посредством электронной почты или для запрета удаления результата. Возврат обработчиком каких-либо значений не предполагается. Ошибки можно возвращать посредством $APPLICATION->ThrowException().

#### Параметры

| Параметр | Описание |
| --- | --- |
| *WEB\_FORM\_ID* | ID веб-формы. |
| *RESULT\_ID* | ID результата. |
| *CHECK\_RIGHTS* | Флаг "Проверять права" (Y|N). |

#### Пример функции-обработчика:

```
public static function my_onBeforeResultDelete($WEB_FORM_ID, $RESULT_ID, $CHECK_RIGHTS)
{
	global $APPLICATION;
  
	// действие обработчика распространяется только на форму с ID=6
	if ($WEB_FORM_ID == 6 && $RESULT_ID == 1) 
	{
		$APPLICATION->ThrowException('Этот результат нельзя удалить!');
	}
}
// зарегистрируем функцию как обработчик события
AddEventHandler('form', 'onBeforeResultDelete', 'my_onBeforeResultDelete');Копировать
```

Новинки документации в соцсетях: