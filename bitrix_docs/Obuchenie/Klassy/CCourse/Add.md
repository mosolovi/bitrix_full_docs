[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CCourse](/api_help/learning/classes/ccourse/index.php)

Add (доступен с 5.0.3)

Add
===

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
int
CCourse::Add(
	array arFields
);Копировать
```

Метод добавляет новый курс. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arFields | Массив Array("поле"=>"значение", ...). Содержит значения [всех полей](/api_help/learning/fields.php#course) курса. Обязательные поля должны быть заполнены.   Дополнительно в поле SITE\_ID должен находиться массив идентификаторов сайтов, к которым привязан добавляемый курс.   Кроме того, с помощью поля "GROUP\_ID", значением которого должен быть массив соответствий кодов групп правам доступа, можно установить права для разных групп на доступ к курсу (см. [CCourse](/api_help/learning/classes/ccourse/index.php)::[SetPermission](/api_help/learning/classes/ccourse/setpermission.php)). |

#### Возвращаемое значение

Метод возвращает идентификатор добавленного курса, если добавление прошло успешно. При возникновении ошибки метод вернет *false*, а в исключениях будут содержаться ошибки.

### Смотрите также

* [CCourse](/api_help/learning/classes/ccourse/index.php)::[Update](/api_help/learning/classes/ccourse/update.php)
* [Поля курса](/api_help/learning/fields.php#course)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$arFields = Array(
		"ACTIVE" => "Y",
		"NAME" => "My First Course",
		"SITE_ID" => Array("ru", "en"), //Sites
		"GROUP_ID" => Array("2" => "R"), //Permissions: Everyone can read my course
		"SORT" => "100",
		"DESCRIPTION" => "It's my first e-Learning course",
		"DESCRIPTION_TYPE" => "text",
	);
	$course = new CCourse;
	$ID = $course->Add($arFields);
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