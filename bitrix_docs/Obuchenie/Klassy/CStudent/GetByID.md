[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CStudent](/api_help/learning/classes/cstudent/index.php)

GetByID (доступен с 5.1.0)

GetByID
=======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
CDBResult
CStudent::GetByID(
	int USER_ID
);Копировать
```

Возвращает учётную запись студента по коду пользователя USER\_ID. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| USER\_ID | Код пользователя. |

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php).

### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)
* [Поля учетной записи студента](/api_help/learning/fields.php#student)
* [CStudent](/api_help/learning/classes/cstudent/index.php)::[GetList](/api_help/learning/classes/cstudent/getlist.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$USER_ID = 3;
    
	$res = CStudent::GetByID($USER_ID);
	if ($arStudent = $res->GetNext())
	{
		echo "CP: ".$arStudent["RESUME"];
	}
}
?>Копировать
```

Новинки документации в соцсетях: