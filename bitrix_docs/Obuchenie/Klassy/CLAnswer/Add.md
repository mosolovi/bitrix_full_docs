[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CLAnswer](/api_help/learning/classes/clanswer/index.php)

Add (доступен с 5.0.6)

Add
===

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
int
CLAnswer::Add(
	array arFields
);Копировать
```

Метод добавляет новый ответ на вопрос. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arFields | Массив Array("поле"=>"значение", ...). Содержит значения [всех полей](/api_help/learning/fields.php#answer) ответа. Обязательные поля должны быть заполнены. |

#### Возвращаемое значение

Метод возвращает идентификатор добавленного ответа, если добавление прошло успешно. При возникновении ошибки метод вернет *false*, а в исключениях будут содержаться ошибки.

#### Смотрите также

* [CLAnswer](/api_help/learning/classes/clanswer/index.php)::[Update](/api_help/learning/classes/clanswer/update.php)
* [Поля ответа](/api_help/learning/fields.php#answer)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$QUESTION_ID = 289;
	$arFields = Array(
		"ANSWER" => "Another answer",
		"QUESTION_ID" => $QUESTION_ID,
	);
	$answer = new CLAnswer;
	$ID = $answer->Add($arFields);
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