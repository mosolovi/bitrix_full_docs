[Веб-формы](/api_help/form/index.php)

[События](/api_help/form/events/index.php)

onBeforeResultAdd (6.5.2)

onBeforeResultAdd
=================

Включить вкладки

Описание и параметры

Пример функции-обработчика

### Описание и параметры

```
функция-обработчик(
	int WEB_FORM_ID,
	array &arFields,
	array &arrVALUES
);Копировать
```

Обработчики события вызываются перед добавлением нового результата веб-формы. Может быть использовано для каких-либо дополнительных проверок или изменения значения полей результата веб-формы. Возврат обработчиком каких-либо значений не предполагается. Ошибки нужно возвращать посредством $APPLICATION->ThrowException().

#### Параметры

| Параметр | Описание |
| --- | --- |
| *WEB\_FORM\_ID* | ID веб-формы. |
| *arFields* | Массив полей результата для записи в БД. |
| *arrVALUES* | Массив значений ответов результата веб-формы. |

#### Смотрите также

* [Событие "onAfterResultAdd"](/api_help/form/events/onafterresultadd.php)
* [Событие "onBeforeResultUpdate"](/api_help/form/events/onbeforeresultupdate.php)

### Пример функции-обработчика

```
public static function my_onBeforeResultAdd($WEB_FORM_ID, &$arFields, &$arrVALUES)
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
AddEventHandler('form', 'onBeforeResultAdd', 'my_onBeforeResultAdd');Копировать
```

Новинки документации в соцсетях: