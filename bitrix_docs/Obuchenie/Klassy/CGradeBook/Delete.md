[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CGradeBook](/api_help/learning/classes/cgradebook/index.php)

Delete (доступен с 5.1.0)

Delete
======

```
bool
CGradeBook::Delete(
	int ID
);Копировать
```

Метод удаляет запись в журнале с идентификатором ID. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор записи. |

#### Возвращаемое значение

Метод возвращает *true* в случае успешного удаления записи, в противном
случае возвращает *false*.

#### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$RECORD_ID = 96;
	@set_time_limit(0);
	$DB->StartTransaction();
	if (!CGradeBook::Delete($RECORD_ID))
	{
		echo "Error!";
		$DB->Rollback();
	}
	else
		$DB->Commit();
}
?>Копировать
```

Новинки документации в соцсетях: