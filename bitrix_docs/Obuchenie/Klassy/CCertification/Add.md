[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CCertification](/api_help/learning/classes/ccertification/index.php)

Add (доступен c 5.1.0)

Add
===

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
int
CCertification::Add(
	array arFields
);Копировать
```

Метод добавляет новый сертификат. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arFields | Массив **Array("поле"=>"значение", ...)**. Содержит значения [всех полей](/api_help/learning/fields.php#certification) сертификата. Обязательные поля должны быть заполнены. |

#### Возвращаемое значение

Метод возвращает идентификатор добавленного сертификата, если добавление
прошло успешно. При возникновении ошибки метод вернет *false*, а в
исключениях будут содержаться ошибки.

#### Смотрите также

* [CCertification](/api_help/learning/classes/ccertification/index.php)::[Update](/api_help/learning/classes/ccertification/update.php)
* [Поля](/api_help/learning/fields.php#certification)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$COURSE_ID = 97;
	$STUDENT_ID = 3;
	$arFields = Array(
		"ACTIVE" => "Y",
		"COURSE_ID" => $COURSE_ID,
		"STUDENT_ID" => $STUDENT_ID,
		"SUMMARY" => 300,
		"MAX_SUMMARY" => 300
	);
	$certificate = new CCertification;
	$ID = $certificate->Add($arFields);
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