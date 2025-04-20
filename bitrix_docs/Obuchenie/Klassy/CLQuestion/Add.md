[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CLQuestion](/api_help/learning/classes/clquestion/index.php)

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
CLQuestion::Add(
	array arFields
);Копировать
```

Метод добавляет новый вопрос. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arFields | Массив **Array("поле"=>"значение", ...)**. Содержит значения [всех полей](/api_help/learning/fields.php#question) вопроса. Обязательные поля должны быть заполнены. |

**Примечание:** при добавлении вопроса средствами API стоит обратить внимание на поле **FILE\_ID**: указать в нем только id файла, уже существующего на сервере, недостаточно. Это поле должно быть массивом, формат подробно описан [здесь](/api_help/main/reference/cfile/savefile.php). (`FILE_ID = CFile::MakeFileArray ('Путь_к_картинке');`)

#### Возвращаемое значение

Метод возвращает идентификатор добавленного вопроса, если добавление прошло
успешно. При возникновении ошибки метод вернет *false*, а в исключениях
будут содержаться ошибки.

### Смотрите также

* [CLQuestion](/api_help/learning/classes/clquestion/index.php)::[Update](/api_help/learning/classes/clquestion/update.php)
* [Поля вопроса](/api_help/learning/fields.php#question)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$LESSON_ID = 431;
	$arFields = Array(
		"ACTIVE" => "Y",
		"LESSON_ID" => $LESSON_ID,
        
		"SORT" => "1",
		"NAME" => "Let us assume that there are several sites in the system. 
			Is it possible to assign users permissions on access to viewing statistics individually for each site?"
	);
	$question = new CLQuestion;
	$ID = $question->Add($arFields);
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