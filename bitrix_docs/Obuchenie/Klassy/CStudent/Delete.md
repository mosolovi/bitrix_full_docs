[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CStudent](/api_help/learning/classes/cstudent/index.php)

Delete (доступен с 5.1.0)

Delete
======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CStudent::Delete(
	int USER_ID
);Копировать
```

Метод удаляет учётную запись студента с кодом пользователя USER\_ID. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| USER\_ID | Код пользователя. |

#### Возвращаемое значение

Метод возвращает *true* в случае успешного удаления учётной записи
студента, в противном случае возвращает *false*.

#### Смотрите также

* [CStudent](/api_help/learning/classes/cstudent/index.php)::[Add](/api_help/learning/classes/cstudent/add.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$USER_ID = 3;
	if ($USER->IsAdmin())
	{
		@set_time_limit(0);
		$DB->StartTransaction();
		if (!CStudent::Delete($USER_ID))
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