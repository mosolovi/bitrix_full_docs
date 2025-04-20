[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CTestResult](/api_help/learning/classes/ctestresult/index.php)

Add (доступен с 5.1.0)

Add
===

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
int
CTestResult::Add(
	array arFields
);Копировать
```

Метод добавляет новый вопрос плана тестирования. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arFields | Массив **Array("поле"=>"значение", ...)**. Содержит значения [всех полей](../../fields.php#test_result) плана тестирования. Обязательные поля должны быть заполнены. |

#### Возвращаемое значение

Метод возвращает идентификатор добавленного вопроса плана тестирования, если
добавление прошло успешно. При возникновении ошибки метод вернёт *false*, а
в исключениях будут содержаться ошибки.

### Смотрите также

* [CTestAttempt](../ctestattempt/index.php)::[CreateAttemptQuestions](../ctestattempt/createattemptquestions.php)
* [CTestResult](index.php)::[Update](update.php)
* [CTestResult](index.php)::[AddResponse](addresponse.php)
* [Поля плана тестирования](../../fields.php#test_result)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$ATTEMPT_ID = 588;
	$QUESTION_ID = 128;
	$arFields = Array(
		"ATTEMPT_ID" => $ATTEMPT_ID,
		"QUESTION_ID" => $QUESTION_ID
	);
	$plan = new CTestResult;
	$ID = $plan->Add($arFields);
	$success = ($ID>0);
	if($success)
	{
		echo "Ok!";
	}
	else
	{
		if($e = $APPLICATION->GetException())
			echo "Error: ".$e->GetString();
	}
}
?>Копировать
```

Новинки документации в соцсетях: