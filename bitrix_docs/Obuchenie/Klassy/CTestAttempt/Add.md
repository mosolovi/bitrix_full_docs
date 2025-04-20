[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CTestAttempt](/api_help/learning/classes/ctestattempt/index.php)

Add (доступен с 5.1.0)

Add
===

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
int
CTestAttempt::Add(
	array arFields
);Копировать
```

Метод добавляет новую попытку. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| Параметр | Массив **Array("поле"=>"значение", ...)**. Содержит значения [всех полей](/api_help/learning/fields.php#attempt) попытки. Обязательные поля должны быть заполнены. |

#### Возвращаемое значение

Метод возвращает идентификатор добавленной попытки, если добавление прошло
успешно. При возникновении ошибки метод вернёт *false*, а в исключениях
будут содержаться ошибки.

#### Смотрите также

* [CTestAttempt](/api_help/learning/classes/ctestattempt/index.php)::[Update](/api_help/learning/classes/ctestattempt/update.php)
* [Поля попытки](/api_help/learning/fields.php#attempt)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$TEST_ID = 32;
	$STUDENT_ID = 3;
	$arFields = Array(
		"TEST_ID" => $TEST_ID,
		"STUDENT_ID" => $STUDENT_ID,
		"STATUS" => "B"
	);
	$attempt = new CTestAttempt;
	$ID = $attempt->Add($arFields);
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