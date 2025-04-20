[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CTest](/api_help/learning/classes/ctest/index.php)

Delete (доступен с 5.1.0)

Delete
======

```
bool
CTest::Delete(
	int ID
);Копировать
```

Метод удаляет тест с идентификатором ID. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор теста. |

#### Возвращаемое значение

Метод возвращает *true* в случае успешного удаления теста, в противном случае возвращает *false*.

#### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$TEST_ID = 99;
	$COURSE_ID = 97;
	if (CCourse::GetPermission($COURSE_ID) >= 'W')
	{
		@set_time_limit(0);
		$DB->StartTransaction();
		if (!CTest::Delete($TEST_ID))
		{
			echo "Error!";
			$DB->Rollback();
		}
		else
			$DB->Commit();
	}
}
?>Копировать
```

Новинки документации в соцсетях: