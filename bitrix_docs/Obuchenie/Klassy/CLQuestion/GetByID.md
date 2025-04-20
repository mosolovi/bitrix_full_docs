[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CLQuestion](/api_help/learning/classes/clquestion/index.php)

GetByID (доступен с 5.0.3)

GetByID
=======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
CDBResult
CLQuestion::GetByID(
	int ID
);Копировать
```

Возвращает вопрос по идентификатору. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор вопроса. |

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php).

#### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)
* [Поля вопроса](/api_help/learning/fields.php#question)
* [CLQuestion](/api_help/learning/classes/clquestion/index.php)::[GetList](/api_help/learning/classes/clquestion/getlist.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$QUESTION_ID = 289;
    
	$res = CLQuestion::GetByID($QUESTION_ID);
	if ($arQuestion = $res->GetNext())
	{
		echo "Name: ".$arQuestion["NAME"];
	}
}
?>Копировать
```

Новинки документации в соцсетях: