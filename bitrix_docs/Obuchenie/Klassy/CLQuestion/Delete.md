[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CLQuestion](/api_help/learning/classes/clquestion/index.php)

Delete (доступен с 5.0.3)

Delete
======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CLQuestion::Delete(
	int ID
);Копировать
```

Метод удаляет вопрос с идентификатором ID. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор вопроса. |

#### Возвращаемое значение

Метод возвращает *true* в случае успешного удаления вопроса, в противном случае возвращает *false*.

#### Смотрите также

* [CLQuestion](/api_help/learning/classes/clquestion/index.php)::[Add](/api_help/learning/classes/clquestion/add.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$COURSE_ID = 97;
	$QUESTION_ID = 600;
	if (CCourse::GetPermission($COURSE_ID) >= 'W')
	{
		@set_time_limit(0);
		$DB->StartTransaction();
		if (!CLQuestion::Delete($QUESTION_ID))
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