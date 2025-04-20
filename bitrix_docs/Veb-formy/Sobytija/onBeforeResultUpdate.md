[Веб-формы](/api_help/form/index.php)

[События](/api_help/form/events/index.php)

onBeforeResultUpdate (6.5.2)

onBeforeResultUpdate
====================

Включить вкладки

Описание и параметры

Пример функции-обработчика

### Описание и параметры

```
функция-обработчик(
	int WEB_FORM_ID,
	int RESULT_ID,
	array &arFields,
	array &arrVALUES,
	string(1) CHECK_RIGHTS
);Копировать
```

Обработчики события вызываются перед сохранением изменений существующего результата веб-формы. Может быть использовано для каких-либо дополнительных проверок или изменения значения полей результата веб-формы. Возврат обработчиком каких-либо значений не предполагается. Ошибки можно возвращать посредством $APPLICATION->ThrowException().

#### Параметры

| Параметр | Описание |
| --- | --- |
| *WEB\_FORM\_ID* | ID веб-формы. |
| *RESULT\_ID* | ID результата. |
| **arFields** | Массив полей результата для записи в БД. |
| *arrVALUES* | Массив значений ответов результата веб-формы. |
| *CHECK\_RIGHTS* | Флаг "Проверять права" (Y|N). |

#### Смотрите также

* [Событие "onAfterResultUpdate"](/api_help/form/events/onafterresultupdate.php)

### Пример функции-обработчика

```
public static function my_onBeforeResultUpdate($WEB_FORM_ID, $RESULT_ID, $arFields, $arrVALUES)
{
	global $APPLICATION;
  
	// действие обработчика распространяется только на форму с ID=6
	if ($WEB_FORM_ID == 6) 
	{
		// в текстовый вопрос с ID=135 должен содержать целое число, большее 5ти.
		$arrVALUES['form_text_135'] = intval($arrVALUES['form_text_135']);
		if ($arrVALUES['form_text_135'] < 5)
		{
			// если значение не подходит - отправим ошибку.
			$APPLICATION->ThrowException('Значение должно быть больше или равно 5!');
		}
	}
}
AddEventHandler('form', 'onBeforeResultUpdate', 'my_onBeforeResultUpdate');Копировать
```

Новинки документации в соцсетях: