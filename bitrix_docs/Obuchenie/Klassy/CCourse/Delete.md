[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CCourse](/api_help/learning/classes/ccourse/index.php)

Delete (доступен с 5.0.3)

Delete
======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CCourse::Delete(
	int ID
);Копировать
```

Метод удаляет курс с идентификатором ID. Метод нестатический.

**Примечание**

Если есть сертификаты, полученные за указанный курс, метод возвратит *false*.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор курса. |

#### Возвращаемое значение

Метод возвращает *true* в случае успешного удаления курса, в противном случае возвращает *false*.

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$ID = 109;//Course ID
	if($USER->IsAdmin())
	{
		@set_time_limit(0);
		$DB->StartTransaction();
		if(!CCourse::Delete($ID))
			$DB->Rollback();
		else
			$DB->Commit();
	}
}
?>Копировать
```

Новинки документации в соцсетях: