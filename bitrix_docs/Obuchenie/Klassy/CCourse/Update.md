[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CCourse](/api_help/learning/classes/ccourse/index.php)

Update (доступен с 5.0.3)

Update
======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
bool
CCourse::Update(
	int   ID,
	array arFields
);Копировать
```

Метод изменяет параметры курса с идентификатором ID. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор изменяемого курса. |
| arFields | Массив Array("поле"=>"значение", ...). Содержит значения [всех полей](/api_help/learning/fields.php#course) курса. Обязательные поля должны быть заполнены.  Дополнительно в поле SITE\_ID должен находиться массив идентификаторов сайтов, к которым привязан добавляемый курс.  Кроме того, с помощью поля "GROUP\_ID", значением которого должен быть массив соответствий кодов групп правам доступа, можно установить права для разных групп на доступ к курсу (см. [CCourse](/api_help/learning/classes/ccourse/index.php)::[SetPermission](/api_help/learning/classes/ccourse/setpermission.php)). |

#### Возвращаемое значение

Метод возвращает *true*, если изменение прошло успешно, при
возникновении ошибки метод вернет *false*. При возникновении ошибки в
исключениях будет содержаться текст ошибки.

### Смотрите также

* [Поля курса](/api_help/learning/fields.php#course)
* [CCourse](/api_help/learning/classes/ccourse/index.php)::[Add](/api_help/learning/classes/ccourse/add.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$arFields = Array(
		"ACTIVE" => "Y",
		"NAME" => "New name",
		"SITE_ID" => Array("en"), //Sites
	);
	$ID = 1;//Course ID
	$course = new CCourse;
	$success = $course->Update($ID, $arFields);
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