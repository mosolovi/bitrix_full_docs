[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CStudent](/api_help/learning/classes/cstudent/index.php)

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
CStudent::Update(
	int   USER_ID,
	array arFields
);Копировать
```

Метод изменяет параметры учётной записи студента с идентификатором ID. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| USER\_ID | Код пользователя. |
| arFields | Массив **Array("поле"=>"значение", ...)**. Содержит значения [всех полей](/api_help/learning/fields.php#student) учетной записи студента. Обязательные поля должны быть заполнены. |

#### Возвращаемое значение

Метод возвращает *true*, если изменение прошло успешно, при
возникновении ошибки метод вернёт *false*. При возникновении ошибки в
исключениях будет содержаться текст ошибки

### Смотрите также

* [Поля учетной записи студента](/api_help/learning/fields.php#student)
* [CStudent](/api_help/learning/classes/cstudent/index.php)::[Add](/api_help/learning/classes/cstudent/add.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$USER_ID = 151;
	$arFields = Array(
		"RESUME" => "My new CP",
	);
	$student = new CStudent;
	$success = $student->Update($USER_ID, $arFields);
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