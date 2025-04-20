[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CGradeBook](/api_help/learning/classes/cgradebook/index.php)

Update (доступен с 5.1.0)

Update
======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CGradeBook::Update(
	int   ID,
	array arFields
);Копировать
```

Метод изменяет параметры записи в журнале с идентификатором ID. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор записи в журнале. |
| arFields | Массив Array("поле"=>"значение", ...). Содержит значения [всех полей](/api_help/learning/fields.php#gradebook) журнала. Обязательные поля должны быть заполнены. |

#### Возвращаемое значение

Метод возвращает *true*, если изменение прошло успешно, при
возникновении ошибки метод вернет *false*. При возникновении ошибки в
исключениях будет содержаться текст ошибки.

#### Смотрите также

* [Поля журнала](/api_help/learning/fields.php#gradebook)
* [CGradeBook](/api_help/learning/classes/cgradebook/index.php)::[Add](/api_help/learning/classes/cgradebook/add.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$RECORD_ID = 96;
	$arFields = Array(
		"RESULT" => 250,
		"MAX_RESULT" => 300
	);
	$gradebook = new CGradeBook;
	$success = $gradebook->Update($RECORD_ID, $arFields);
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