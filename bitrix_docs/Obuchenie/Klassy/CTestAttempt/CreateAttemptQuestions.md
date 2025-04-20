[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CTestAttempt](/api_help/learning/classes/ctestattempt/index.php)

CreateAttemptQuestions (доступен с 5.1.0)

CreateAttemptQuestions
======================

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CTestAttempt::CreateAttemptQuestions(
	int ATTEMPT_ID
);Копировать
```

Создаёт план вопросов для указанной попытки. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ATTEMPT\_ID | Идентификатор попытки. |

#### Возвращаемое значение

Метод возвращает *true*, если создание плана вопросов прошло успешно.
При возникновении ошибки метод вернёт *false*, а в исключениях будут
содержаться ошибки.

#### Смотрите также

* [CTestResult](/api_help/learning/classes/ctestresult/index.php)::[Add](/api_help/learning/classes/ctestresult/add.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$ATTEMPT_ID = 563;
	$success = CTestAttempt::CreateAttemptQuestions($ATTEMPT_ID);
	if($success)
	{
		echo "Questions have been created.";
	}
	else
	{
		if($ex = $APPLICATION->GetException())
			echo "Error: ".$ex->GetString();
	}
}
?>Копировать
```

Новинки документации в соцсетях: