[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskReminders](/api_help/tasks/classes/ctaskreminders/index.php)

DeleteByUserID (10.0.6)

DeleteByUserID
==============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CTaskReminders::DeleteByUserID(
	USER_ID
);Копировать
```

Метод удаляет напоминания пользователя с идентификатором **USER\_ID**.

**Примечание:** Метод принимает массив конфигурационных параметров и генерирует скрипты, необходимые для показа файлового диалога. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| USER\_ID | Идентификатор пользователя. |

#### Возвращаемое значение

Метод возвращает **true** в случае успешного удаления связи, в противном случае возвращает **false**.

### Примеры использования

```
<?
if (CModule::IncludeModule("tasks"))
{
	$USER_ID = 4;
	if($USER->IsAdmin())
	{
		CTaskReminders::DeleteByUserID($USER_ID);
	}
}
?>Копировать
```

Новинки документации в соцсетях: