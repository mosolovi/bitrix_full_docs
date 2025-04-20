[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CTestResult](/api_help/learning/classes/ctestresult/index.php)

Delete (доступен с 5.1.0)

Delete
======

```
bool
CTestResult::Delete(
	int ID
);Копировать
```

Метод удаляет вопрос плана тестирования с идентификатором ID. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор вопроса в плане тестирования. |

#### Возвращаемое значение

Метод возвращает *true* в случае успешного удаления результата
тестирования, в противном случае возвращает *false*.

#### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$TEST_RESULT_ID = 2967;
	@set_time_limit(0);
	$DB->StartTransaction();
	if (!CTestResult::Delete($TEST_RESULT_ID))
	{
		echo "Error!";
		$DB->Rollback();
	}
	else
		$DB->Commit();
}
?>Копировать
```

Новинки документации в соцсетях: