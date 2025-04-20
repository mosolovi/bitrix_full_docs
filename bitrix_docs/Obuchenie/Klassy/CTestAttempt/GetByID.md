[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CTestAttempt](/api_help/learning/classes/ctestattempt/index.php)

GetByID (доступен с 5.1.0)

GetByID
=======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
CDBResult
CTestAttempt::GetByID(
	int ID
);Копировать
```

Возвращает попытку по идентификатору ID. Учитываются права доступа текущего
пользователя. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор попытки. |

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php).

#### Смотрите также

- [CDBResult](/api_help/main/reference/cdbresult/index.php)
- [Поля попытки](/api_help/learning/fields.php#attempt)
- [CTestAttempt](/api_help/learning/classes/ctestattempt/index.php)::[GetList](/api_help/learning/classes/ctestattempt/getlist.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$ATTEMPT_ID = 590;
    
	$res = CTestAttempt::GetByID($ATTEMPT_ID);
	if ($arAttempt = $res->GetNext())
	{
		echo "Test name: ".$arAttempt["TEST_NAME"];
		echo "Date start: ".$arAttempt["DATE_START"];
	}
}
?>Копировать
```

Новинки документации в соцсетях: