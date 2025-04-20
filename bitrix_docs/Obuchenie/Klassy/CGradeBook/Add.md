[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CGradeBook](/api_help/learning/classes/cgradebook/index.php)

Add (доступен с 5.1.0)

Add
===

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
int
CGradeBook::Add(
	array arFields
);Копировать
```

Метод добавляет новую запись в журнал. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arFields | Массив **Array("поле"=>"значение", ...)**. Содержит значения [всех полей](/api_help/learning/fields.php#gradebook) журнала. Обязательные поля должны быть заполнены. |

#### Возвращаемое значение

Метод возвращает идентификатор добавленной записи в журнал, если добавление
прошло успешно. При возникновении ошибки метод вернёт *false*, а в
исключениях будут содержаться ошибки.

#### Смотрите также

* [CGradeBook](/api_help/learning/classes/cgradebook/index.php)::[Update](/api_help/learning/classes/cgradebook/update.php)
* [Поля журнала](/api_help/learning/fields.php#gradebook)

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
		"RESULT" => 300,
		"MAX_RESULT" => 300
	);
	$gradebook = new CGradeBook;
	$ID = $gradebook->Add($arFields);
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