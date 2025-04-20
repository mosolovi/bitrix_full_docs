[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CTest](/api_help/learning/classes/ctest/index.php)

GetByID (доступен с 5.1.0)

GetByID
=======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
CDBResult
CTest::GetByID(
	int ID
);Копировать
```

Возвращает тест по идентификатору ID. Учитываются права доступа текущего
пользователя. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор теста. |

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php).

#### Смотрите также

- [CDBResult](/api_help/main/reference/cdbresult/index.php)
- [Поля теста](/api_help/learning/fields.php#test)
- [CTest](/api_help/learning/classes/ctest/index.php)::[GetList](/api_help/learning/classes/ctest/getlist.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$TEST_ID = 32;
    
	$res = CTest::GetByID($TEST_ID);
	if ($arTest = $res->GetNext())
	{
		echo "Test name: ".$arTest["NAME"];
	}
}
?>Копировать
```

Новинки документации в соцсетях: