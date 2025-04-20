[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CChapter](/api_help/learning/classes/cchapter/index.php)

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
CChapter::Update(
	int   ID,
	array arFields
);Копировать
```

Метод изменяет параметры главы с идентификатором ID.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор главы. |
| arFields | Массив Array("поле"=>"значение", ...). Содержит значения [всех полей](/api_help/learning/fields.php#chapter) главы. Обязательные поля должны быть заполнены. |

#### Возвращаемое значение

Метод возвращает *true*, если изменение прошло успешно, при возникновении ошибки метод вернет *false*. При возникновении ошибки в исключениях будет содержаться текст ошибки.

### Смотрите также

* [Поля главы](/api_help/learning/fields.php#chapter)
* [CChapter](/api_help/learning/classes/cchapter/index.php)::[Add](/api_help/learning/classes/cchapter/add.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$CHAPTER_ID = 299;
	$arFields = Array(
		"ACTIVE" => "N",
		"NAME" => "New name of Chapter 1",
		"SORT" => "555",
	);
	$chapter = new CChapter;
	$success = $chapter->Update($CHAPTER_ID, $arFields);
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