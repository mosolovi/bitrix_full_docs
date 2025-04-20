[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CLQuestion](/api_help/learning/classes/clquestion/index.php)

Update (доступен с 5.0.3)

Update
======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
bool
CLQuestion::Update(
	int   ID,
	array arFields
);Копировать
```

Метод изменяет параметры вопроса с идентификатором ID. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор вопроса. |
| arFields | Массив **Array("поле"=>"значение", ...)**. Содержит значения [всех полей](/api_help/learning/fields.php#question) вопроса. Обязательные поля должны быть заполнены. |

#### Возвращаемое значение

Метод возвращает *true*, если изменение прошло успешно, при
возникновении ошибки метод вернёт *false*. При возникновении ошибки в
исключениях будет содержаться текст ошибки.

### Смотрите также

* [Поля вопроса](/api_help/learning/fields.php#question)
* [CLQuestion](/api_help/learning/classes/clquestion/index.php)::[Add](/api_help/learning/classes/clquestion/add.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$QUESTION_ID = 600;
	$arFields = Array(
		"ACTIVE" => "N",
		"NAME" => "New name of question",
		"SORT" => "555",
	);
	$question = new CLQuestion;
	$success = $question->Update($QUESTION_ID, $arFields);
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