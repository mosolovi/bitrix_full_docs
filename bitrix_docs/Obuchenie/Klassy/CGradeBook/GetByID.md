[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CGradeBook](/api_help/learning/classes/cgradebook/index.php)

GetByID (доступен с 5.1.0)

GetByID
=======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
CDBResult
CGradeBook::GetByID(
	int ID
);Копировать
```

Возвращает запись журнала по идентификатору ID. Учитываются права доступа текущего пользователя. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор записи в журнале. |

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php).

#### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)
* [Поля журнала](/api_help/learning/fields.php#gradebook)
* [CGradeBook](/api_help/learning/classes/cgradebook/index.php)::[GetList](/api_help/learning/classes/cgradebook/getlist.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$RECORD_ID = 95;
    
	$res = CGradeBook::GetByID($RECORD_ID);
	if ($arGradeBook = $res->GetNext())
	{
		echo "Test: ".$arGradeBook["TEST_NAME"]." User: ".$arGradeBook["USER_NAME"]." Score: ".$arGradeBook["RESULT"];
	}
}
?>Копировать
```

Новинки документации в соцсетях: