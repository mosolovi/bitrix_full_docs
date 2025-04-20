[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTasks](/api_help/tasks/classes/ctasks/index.php)

AddFiles (10.0.2 - устарел с версии 12.0.9)

AddFiles
========

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
void
CTasks::AddFiles(
	ID,
	array arFiles,
	array arParams = array()
);Копировать
```

Метод добавляет файлы к задаче.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| ID | Идентификатор задачи, к которой добавляются файлы |  |
| arFiles | Массив идентификаторов файлов |  |
| arParams | Массив дополнительных параметров:  * **USER\_ID** - ID пользователя, от имени которого будет загружаться файл; * **CHECK\_RIGHTS\_ON\_FILES** - проверять права на файл (**Y**/**N**).  Необязательный. | 12.5.0 |

#### Возвращаемое значение

Метод не имеет возвращаемого значения.

### Примеры использования

```
<?
if (CModule::IncludeModule("tasks"))
{
	$ID = 1;
	$arFiles = array(102, 34, 5);
	CTasks::AddFiles($ID, $arFiles);
}
?>Копировать
```

Прикрепить к задаче файл с диска:

```
use Bitrix\Main\Loader;
use Bitrix\Tasks\Control\Task;
if (!Loader::includeModule('tasks'))
{
	return;
}
$userId = 1;
$taskId = 1367;
$diskFileId = 150;
$handler = new Task($userId);
try
{
	$task = $handler->update($taskId, [
		'UF_TASK_WEBDAV_FILES' => [
			'n' . $diskFileId,
		],
	]);
}
catch (Exception $exception)
{
}Копировать
```

Новинки документации в соцсетях: