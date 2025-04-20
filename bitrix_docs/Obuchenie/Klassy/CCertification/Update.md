[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CCertification](/api_help/learning/classes/ccertification/index.php)

Update (доступен c 5.1.0)

Update
======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
bool
CCertification::Update(
	int   ID,
	array arFields
);Копировать
```

Метод изменяет параметры сертификата с идентификатором ID. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор сертификата. |
| arFields | Массив Array("поле"=>"значение", ...). Содержит значения [всех полей](/api_help/learning/fields.php#certification) сертификата. Обязательные поля должны быть заполнены. |

#### Возвращаемое значение

Метод возвращает *true*, если изменение прошло успешно, при
возникновении ошибки функция вернет *false*. При возникновении ошибки в
исключениях будет содержаться текст ошибки

### Смотрите также

* [Поля](/api_help/learning/fields.php#certification)
* [CCertification](/api_help/learning/classes/ccertification/index.php)::[Add](/api_help/learning/classes/ccertification/add.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$CERTIFICATE_ID = 15;
	$arFields = Array(
		"ACTIVE" => "N",
		"SUMMARY" => 290,
		"MAX_SUMMARY" => 555
	);
	$certificate = new CCertification;
	$success =  $certificate->Update($CERTIFICATE_ID, $arFields);
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