[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CChapter](/api_help/learning/classes/cchapter/index.php)

Delete (доступен с 5.1.0, устарел и удален с 12.0.0)

Delete
======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CChapter::Delete(
	int ID
);Копировать
```

Метод удаляет главу с идентификатором ID.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор главы. |

#### Возвращаемое значение

Метод возвращает *true* в случае успешного удаления главы, в противном случае возвращает *false*.

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$COURSE_ID = 97;
	$CHAPTER_ID = 300;
	if (CCourse::GetPermission($COURSE_ID) >= 'W')
	{
		@set_time_limit(0);
		$DB->StartTransaction();
		if (!CChapter::Delete($CHAPTER_ID))
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