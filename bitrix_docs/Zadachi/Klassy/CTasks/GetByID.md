[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTasks](/api_help/tasks/classes/ctasks/index.php)

GetByID (10.0.2 - 12.0.9)

GetByID
=======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
CDBResult
CTasks::GetByID(
	int ID,
	bool bCheckPermissions = true,
	array arParams = array()
);Копировать
```

Возвращает поля задачи по ее идентификатору.

**Примечание:** Метод принимает массив конфигурационных параметров и генерирует скрипты, необходимые для показа файлового диалога. Метод статический.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| ID | Идентификатор задачи. |  |
| bCheckPermissions | Флаг проверки прав доступа к задаче. Необязательный параметр. По умолчанию равен *true*. | 10.0.2 |
| arParams | Массив дополнительных параметров. Необязательный. | 11.5.6 |

#### Возвращаемое значение

Возвращается объект CDBResult.

### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("tasks"))
{
	$rsTask = CTasks::GetByID(332);
	if ($arTask = $rsTask->GetNext())
	{
		echo $arTask["TITLE"];
	}
}
?>Копировать
```

Новинки документации в соцсетях: