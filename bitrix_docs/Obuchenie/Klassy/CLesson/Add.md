[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CLesson](/api_help/learning/classes/clesson/index.php)

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
CLesson::Add(
	array arFields
);Копировать
```

Метод добавляет новый урок.

**Примечание:** начиная с версии 12.0.0, метод считается устаревшим. Вместо него для работы с главами/уроками следует использовать класс **CLearnLesson**.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arFields | Массив **Array("поле"=>"значение", ...)**. Содержит значения [всех полей](/api_help/learning/fields.php#lesson) урока. Обязательные поля должны быть заполнены. |

#### Возвращаемое значение

Метод возвращает идентификатор добавленного урока, если добавление прошло
успешно. При возникновении ошибки метод вернёт *false*, а в исключениях
будут содержаться ошибки.

### Смотрите также

* [CLesson](/api_help/learning/classes/clesson/index.php)::[Update](/api_help/learning/classes/clesson/update.php)
* [Поля урока](/api_help/learning/fields.php#lesson)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$COURSE_ID = 97;
	$arFields = Array(
		"ACTIVE" => "Y",
		"COURSE_ID" => $COURSE_ID,
		"NAME" => "Lesson 1",
		"SORT" => "1",
		"DETAIL_TEXT" => "It my first lesson ...",
	);
	$lesson = new CLesson;
	$ID = $lesson->Add($arFields);
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