[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CTestAttempt](/api_help/learning/classes/ctestattempt/index.php)

Delete (доступен с 5.1.0)

Delete
======

```
bool
CTestAttempt::Delete(
	int ID
);Копировать
```

Метод удаляет попытку с идентификатором ID. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор попытки. |

#### Возвращаемое значение

Метод возвращает *true* в случае успешного удаления попытки, в противном
случае возвращает *false*.

#### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$COURSE_ID = 83;
	$ATTEMPT_ID = 596;
	if (CCourse::GetPermission($COURSE_ID) >= 'W')
	{
		@set_time_limit(0);
		$DB->StartTransaction();
		if (!CTestAttempt::Delete($ATTEMPT_ID))
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