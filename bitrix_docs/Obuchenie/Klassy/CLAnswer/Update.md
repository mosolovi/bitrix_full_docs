[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CLAnswer](/api_help/learning/classes/clanswer/index.php)

Update (доступен с 5.0.6)

Update
======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
bool
CLAnswer::Update(
	int   ID,
	array arFields
);Копировать
```

Метод изменяет параметры ответа с идентификатором ID. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор ответа. |
| arFields | Массив Array("поле"=>"значение", ...). Содержит значения [всех полей](/api_help/learning/fields.php#answer) ответа. Обязательные поля должны быть заполнены. |

#### Возвращаемое значение

Метод возвращает *true*, если изменение прошло успешно, при
возникновении ошибки метод вернет *false*. При возникновении ошибки в
исключениях будет содержаться текст ошибки.

### Смотрите также

* [Поля ответа](/api_help/learning/fields.php#answer)
* [CLAnswer](/api_help/learning/classes/clanswer/index.php)::[Add](/api_help/learning/classes/clanswer/add.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$ANSWER_ID = 1553;
	$arFields = Array(
		"ANSWER" => "New answer name",
		"SORT" => "1",
	);
	$answer = new CLAnswer;
	$success = $answer->Update($ANSWER_ID, $arFields);
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