[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CTest](/api_help/learning/classes/ctest/index.php)

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
CTest::Add(
	array arFields
);Копировать
```

Метод добавляет новый тест. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arFields | Массив **Array("поле"=>"значение", ...)**. Содержит значения [всех полей](/api_help/learning/fields.php#test) теста. Обязательные поля должны быть заполнены. |

#### Возвращаемое значение

Метод возвращает идентификатор добавленного теста, если добавление прошло
успешно. При возникновении ошибки метод вернёт *false*, а в исключениях
будут содержаться ошибки.

### Смотрите также

* [CTest](/api_help/learning/classes/ctest/index.php)::[Update](/api_help/learning/classes/ctest/update.php)
* [Поля теста](/api_help/learning/fields.php#test)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$COURSE_ID = 97;
	$arFields = Array(
		"COURSE_ID" => $COURSE_ID,
		"NAME" => "New test!",
		"INCLUDE_SELF_TEST" => "Y"
	);
	$test = new CTest;
	$ID = $test->Add($arFields);
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