[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CLAnswer](/api_help/learning/classes/clanswer/index.php)

GetByID (доступен с 5.0.6)

GetByID
=======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
CDBResult
CLAnswer::GetByID(
	int ID
);Копировать
```

Возвращает ответ по его коду ID. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор ответа. |

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php).

#### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)
* [Поля ответа](/api_help/learning/fields.php#answer)
* [CLAnswer](/api_help/learning/classes/clanswer/index.php)::[GetList](/api_help/learning/classes/clanswer/getlist.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$ANSWER_ID = 573;
    
	$res = CLAnswer::GetByID($ANSWER_ID);
	if ($arAnswer = $res->GetNext())
	{
		echo "Name: ".$arAnswer["ANSWER"];
	}
}
?>Копировать
```

Новинки документации в соцсетях: