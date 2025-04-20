[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CStudent](/api_help/learning/classes/cstudent/index.php)

Add (доступен с 5.1.0)

Add
===

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
int
CStudent::Add(
	array arFields
);Копировать
```

Метод добавляет новую учетную запись студента. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arFields | Массив Array("поле"=>"значение", ...). Содержит значения [всех полей](/api_help/learning/fields.php#student) учётной записи студента. Обязательные поля должны быть заполнены. |

#### Возвращаемое значение

Метод возвращает идентификатор добавленной учетной записи студента (равный [коду
пользователя](/api_help/main/reference/cuser/index.php)), если добавление прошло успешно. При возникновении ошибки
метод вернёт *false*, а в исключениях будут содержаться ошибки.

### Смотрите также

* [CStudent](/api_help/learning/classes/cstudent/index.php)::[Update](/api_help/learning/classes/cstudent/update.php)
* [Поля учетной записи студента](/api_help/learning/fields.php#student)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$arFields = Array(
		"USER_ID" => 151,
		"RESUME" => "My resume"
	);
	$student = new CStudent;
	$ID = $student->Add($arFields);
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