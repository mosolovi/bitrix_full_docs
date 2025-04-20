[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CChapter](/api_help/learning/classes/cchapter/index.php)

Add (доступен с 5.1.0, устарел и удален с 12.0.0)

Add
===

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
int
CChapter::Add(
	array arFields
);Копировать
```

Метод добавляет новую главу.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arFields | Массив Array("поле"=>"значение", ...). Содержит значения [всех полей](/api_help/learning/fields.php#chapter) главы. Обязательные поля должны быть заполнены. |

#### Возвращаемое значение

Метод возвращает идентификатор добавленной главы, если добавление прошло успешно. При возникновении ошибки метод вернет *false*, а в исключениях будут содержаться ошибки.

### Смотрите также

* [CChapter](/api_help/learning/classes/cchapter/index.php)::[Update](/api_help/learning/classes/cchapter/update.php)
* [Поля главы](/api_help/learning/fields.php#chapter)

### Примеры использования

```
if (CModule::IncludeModule("learning"))
{
	$COURSE_ID = 97;
	$arFields = Array(
		"COURSE_ID" => $COURSE_ID,
		"ACTIVE" => "Y",
		"NAME" => "Chapter 1",
		"SORT" => "100",
		"DETAIL_TEXT" => "In this chapter ...",
	);
	$chapter = new CChapter;
	$ID = $chapter->Add($arFields);
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