[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CTestAttempt](/api_help/learning/classes/ctestattempt/index.php)

AttemptFinished (доступен с 5.1.0)

AttemptFinished
===============

```
bool
CTestAttempt::AttemptFinished(
	int ATTEMPT_ID
);Копировать
```

Переводит попытку в статус "Закончена" и пересчитывает набранные баллы. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ATTEMPT\_ID | Идентификатор попытки. |

#### Возвращаемое значение

Метод возвращает *true*, если операция выполнилась успешно, иначе
*false*.

#### Смотрите также

* [CTestAttempt](/api_help/learning/classes/ctestattempt/index.php)::[Update](/api_help/learning/classes/ctestattempt/update.php)

#### Примеры использования

```
if (CModule::IncludeModule("learning"))
{
	$ATTEMPT_ID = 23;
	$oTestAttempt = new CTestAttempt;
	$success = $oTestAttempt->AttemptFinished($ATTEMPT_ID);
	if ($success)
		echo "Attempt has been finished";
	else
		echo "Error!";
}Копировать
```

Новинки документации в соцсетях: