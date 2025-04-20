[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CTestAttempt](/api_help/learning/classes/ctestattempt/index.php)

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
CTestAttempt::Update(
	int   ID,
	array arFields
);Копировать
```

Метод изменяет параметры попытки с идентификатором ID. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор попытки |
| arFields | Массив Array("поле"=>"значение", ...). Содержит значения [всех полей](/api_help/learning/fields.php#attempt) попытки. Обязательные поля должны быть заполнены. |

#### Возвращаемое значение

Метод возвращает *true*, если изменение прошло успешно, при
возникновении ошибки метод вернёт *false*. При возникновении ошибки в
исключениях будет содержаться текст ошибки.

### Смотрите также

* [Поля попытки](/api_help/learning/fields.php#attempt)
* [CTestAttempt](/api_help/learning/classes/ctestattempt/index.php)::[Add](/api_help/learning/classes/ctestattempt/add.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$ATTEMPT_ID = 596;
	$arFields = Array(
		"STATUS" => "F",
		"DATE_END" => ConvertTimeStamp(false,"FULL")
	);
	$attempt = new CTestAttempt;
	$ID = $attempt->Update($ATTEMPT_ID, $arFields);
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