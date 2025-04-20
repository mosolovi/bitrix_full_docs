[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskReminders](/api_help/tasks/classes/ctaskreminders/index.php)

DeleteByDate (10.0.6)

DeleteByDate
============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CTaskReminders::DeleteByDate(
	REMIND_DATE
);Копировать
```

Метод удаляет напоминания с датой **REMIND\_DATE**.

**Примечание:** Метод принимает массив конфигурационных параметров и генерирует скрипты, необходимые для показа файлового диалога. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| REMIND\_DATE | Дата напоминания. |

#### Возвращаемое значение

Метод возвращает *true* в случае успешного удаления связи, в противном случае возвращает *false*.

### Примеры использования

```
<?
if (CModule::IncludeModule("tasks"))
{
	$REMIND_DATE = "2011-11-01";
	if($USER->IsAdmin())
	{
		CTaskReminders::DeleteByDate($REMIND_DATE);
	}
}
?>Копировать
```

Новинки документации в соцсетях: