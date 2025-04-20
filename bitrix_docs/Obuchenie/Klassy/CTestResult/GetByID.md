[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CTestResult](/api_help/learning/classes/ctestresult/index.php)

GetByID (доступен с 5.1.0)

GetByID
=======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
CDBResult
CTestResult::GetByID(
	int ID
);Копировать
```

Возвращает вопрос плана тестирования по идентификатору ID. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор вопроса в плане тестирования. |

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php).

### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)
* [Поля плана тестирования](../../fields.php#test_result)
* [CTestResult](index.php)::[GetList](getlist.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$TEST_RESULT_ID = 2894;
    
	$res = CTestResult::GetByID($TEST_RESULT_ID);
	if ($arResult = $res->GetNext())
	{
		echo " Question name: ".$arResult["QUESTION_NAME"];
		echo " Answered: ".$arResult["ANSWERED"];
		echo " Point: ".$arResult["POINT"];
	}
}
?>Копировать
```

Новинки документации в соцсетях: