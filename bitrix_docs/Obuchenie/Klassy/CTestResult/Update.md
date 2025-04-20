[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CTestResult](/api_help/learning/classes/ctestresult/index.php)

Update (доступен с 5.1.0)

Update
======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
bool
CTestResult::Update(
	int   ID,
	array arFields
);Копировать
```

Метод изменяет параметры вопроса плана тестирования с идентификатором ID. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор вопроса в плане тестирования. |
| arFields | Массив Array("поле"=>"значение", ...). Содержит значения [всех полей](../../fields.php#test_result) плана тестирования. Обязательные поля должны быть заполнены. |

#### Возвращаемое значение

Метод возвращает *true*, если изменение прошло успешно, при
возникновении ошибки метгод вернёт *false*. При возникновении ошибки в
исключениях будет содержаться текст ошибки.

### Смотрите также

* [Поля плана
  тестирования](../../fields.php#test_result)
* [CTestResult](index.php)::[Add](add.php)
* [CTestResult](index.php)::[AddResponse](addresponse.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$TEST_TESULT_ID = 2962;
	$arFields = Array(
		"CORRECT" => "Y",
		"POINT" => "20"
	);
	$plan = new CTestResult;
	$success = $plan->Update($TEST_TESULT_ID, $arFields);
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