[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CCertification](/api_help/learning/classes/ccertification/index.php)

Delete (доступен c 5.1.0)

Delete
======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CCertification::Delete(
	int ID
);Копировать
```

Метод удаляет сертификат с идентификатором ID. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор сертификата. |

#### Возвращаемое значение

Метод возвращает *true* в случае успешного удаления сертификата, в
противном случае возвращает *false*.

#### Смотрите также

* [CCertification](/api_help/learning/classes/ccertification/index.php)::[Add](/api_help/learning/classes/ccertification/add.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$COURSE_ID = 97;
	$CERTIFICATE_ID = 19;
	if (CCourse::GetPermission($COURSE_ID) >= 'W')
	{
		@set_time_limit(0);
		$DB->StartTransaction();
		if (!CCertification::Delete($CERTIFICATE_ID))
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