[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CTestResult](/api_help/learning/classes/ctestresult/index.php)

AddResponse (доступен с 5.1.0)

AddResponse
===========

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CTestResult::AddResponse(
	int TEST_RESULT_ID
	mixed RESPONSE
);Копировать
```

Сохраняет ответ учащегося и устанавливает, дан ли на вопрос правильный ответ. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| TEST\_RESULT\_ID | Идентификатор вопроса в плане тестирования. |
| RESPONSE | Идентификатор или массив идентификаторов [ответов на вопрос](../../fields.php#answer). |

#### Возвращаемое значение

Метод возвращает *true*, если изменение прошло успешно, при
возникновении ошибки метод вернёт *false*. При возникновении ошибки в
исключениях будет содержаться текст ошибки.

#### Смотрите также

* [CTestResult](index.php)::[Update](update.php)

### Примеры использования

```
if (CModule::IncludeModule("learning"))
{
	$TEST_TESULT_ID = 2962;
	$RESPONSE = 186; /* or Array(186,187); */
	$res = CTestResult::AddResponse($TEST_RESULT_ID, $RESPONSE);
	if($res)
		echo "Response has been added ";
	else
		echo "Error";
}Копировать
```

Новинки документации в соцсетях: