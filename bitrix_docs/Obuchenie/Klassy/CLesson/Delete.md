[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CLesson](/api_help/learning/classes/clesson/index.php)

Delete (доступен с 5.1.0, устарел и удален с 12.0.0)

Delete
======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CLesson::Delete(
	int ID
);Копировать
```

Метод удаляет урок с идентификатором ID.

**Примечание:** начиная с версии 12.0.0, метод считается устаревшим. Вместо него для работы с главами/уроками следует использовать класс **CLearnLesson**.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор урока. |

#### Возвращаемое значение

Метод возвращает *true* в случае успешного удаления урока, в противном
случае возвращает *false*.

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$COURSE_ID = 97;
	$LESSON_ID = 732;
	if (CCourse::GetPermission($COURSE_ID) >= 'W')
	{
		@set_time_limit(0);
		$DB->StartTransaction();
		if (!CLesson::Delete($LESSON_ID))
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