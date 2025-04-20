[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CLAnswer](/api_help/learning/classes/clanswer/index.php)

Delete (доступен с 5.0.6)

Delete
======

```
bool
CLAnswer::Delete(
	int ID
);Копировать
```

Метод удаляет ответ с идентификатором ID. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор ответа. |

#### Возвращаемое значение

Метод возвращает *true* в случае успешного удаления ответа, в противном случае возвращает *false*.

#### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$COURSE_ID = 97;
	$ANSWER_ID = 1553;
	if (CCourse::GetPermission($COURSE_ID) >= 'W')
	{
		@set_time_limit(0);
		$DB->StartTransaction();
		if (!CLAnswer::Delete($ANSWER_ID))
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