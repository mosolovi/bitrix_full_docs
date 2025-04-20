[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CLesson](/api_help/learning/classes/clesson/index.php)

Update (доступен с 5.1.0, устарел и удален с 12.0.0)

Update
======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
bool
CLesson::Update(
	int   ID,
	array arFields
);Копировать
```

Метод изменяет параметры урока с идентификатором ID.

**Примечание:** начиная с версии 12.0.0, метод считается устаревшим. Вместо него для работы с главами/уроками следует использовать класс **CLearnLesson**.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор урока. |
| arFields | Массив **Array("поле"=>"значение", ...)**. Содержит значения [всех полей](/api_help/learning/fields.php#lesson) урока. Обязательные поля должны быть заполнены. |

#### Возвращаемое значение

Метод возвращает *true*, если изменение прошло успешно, при
возникновении ошибки метод вернёт *false*. При возникновении ошибки в
исключениях будет содержаться текст ошибки.

### Смотрите также

* [Поля урока](/api_help/learning/fields.php#lesson)
* [CLesson](/api_help/learning/classes/clesson/index.php)::[Add](/api_help/learning/classes/clesson/add.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$LESSON_ID = 732;
	$arFields = Array(
		"ACTIVE" => "N",
		"NAME" => "New name of Lesson 1",
		"SORT" => "555",
	);
	$lesson = new CLesson;
	$success = $lesson->Update($LESSON_ID, $arFields);
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