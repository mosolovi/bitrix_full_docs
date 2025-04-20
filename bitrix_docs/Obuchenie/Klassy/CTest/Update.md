[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CTest](/api_help/learning/classes/ctest/index.php)

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
CTest::Update(
	int   ID,
	array arFields
);Копировать
```

Метод изменяет параметры теста с идентификатором ID. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор теста. |
| arFields | Массив Array("поле"=>"значение", ...). Содержит значения [всех полей](/api_help/learning/fields.php#test) теста. Обязательные поля должны быть заполнены. |

#### Возвращаемое значение

Метод возвращает *true*, если изменение прошло успешно, при возникновении ошибки метод вернет *false*. При возникновении ошибки в исключениях будет содержаться текст ошибки.

### Смотрите также

* [Поля теста](/api_help/learning/fields.php#test)
* [CTest](/api_help/learning/classes/ctest/index.php)::[Add](/api_help/learning/classes/ctest/add.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$TEST_ID = 99;
	$arFields = Array(
		"NAME" => "New name",
		"INCLUDE_SELF_TEST" => "N",
		"QUESTIONS_AMOUNT" => 5
	);
	$test = new CTest;
	$success = $test->Update($TEST_ID, $arFields);
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