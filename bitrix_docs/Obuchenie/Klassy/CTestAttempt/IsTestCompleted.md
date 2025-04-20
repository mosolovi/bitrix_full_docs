[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CTestAttempt](/api_help/learning/classes/ctestattempt/index.php)

IsTestCompleted (доступен с 5.1.0)

IsTestCompleted
===============

```
bool
CTestAttempt::IsTestCompleted(
	int ATTEMPT_ID
	int PERCENT
);Копировать
```

Проверяет, пройден ли тест. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ATTEMPT\_ID | Идентификатор попытки. |
| PERCENT | Количество процентов, необходимых для прохождения теста. |

#### Возвращаемое значение

Метод возвращает *true*, если тест пройден, иначе - *false*.

#### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$ATTEMPT_ID = 563;
	$PERCENT = 30;
	$complete = CTestAttempt::IsTestCompleted($ATTEMPT_ID, $PERCENT);
	if ($complete)
		echo "Test has been completed";
	else
		echo "Try again";
}
?>Копировать
```

Новинки документации в соцсетях: