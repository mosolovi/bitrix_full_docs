[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskItem](/api_help/tasks/classes/ctaskitem/index.php)

update (с версии 12.5.3)

update
======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CTaskItem::Update(
	array arFields
);Копировать
```

Нестатический метод изменяет параметры задачи с идентификатором ID.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| arFields | Массив Array("поле"=>"значение", ...). Содержит значения всех полей задачи. Обязательные поля должны быть заполнены. | 16.0.0 |

#### Возвращаемое значение

При возникновении ошибки в исключениях будет содержаться текст ошибки.

### Примеры использования

```
// смена ответственного в задаче
CModule::IncludeModule('tasks');
global $USER;
$userId = $USER->GetID();
$taskId = 85;
$oTaskItem = new CTaskItem($taskId, $userId);
try
{
	$rs = $oTaskItem->Update(array("RESPONSIBLE_ID" => 480));
}
catch(Exception $e)
{
	print('Error');
}
// прикрепление файла к задаче
CModule::IncludeModule('tasks');
$storage = Bitrix\Disk\Driver::getInstance()->getStorageByUserId($USER_ID);
$folder = $storage->getFolderForUploadedFiles();
$arFile = CFile::MakeFileArray($_SERVER["DOCUMENT_ROOT"]."/upload/wlog.txt");
$file = $folder->uploadFile($arFile, array(
	'NAME' => $arFile["name"],
	'CREATED_BY' => $USER_ID
), array(), true);
$FILE_ID = $file->getId();
$oTaskItem = new CTaskItem($taskId, $userId);
$rs = $oTaskItem->Update(array("UF_TASK_WEBDAV_FILES" => Array("n$FILE_ID")));Копировать
```

Добавление файла к задаче, где уже есть добавленные файлы. В примере выше добавляемый файл перезаписывается.

```
$taskId = 183; //Id задачи
$userId = 1; // Id пользователя, от которого изменяем задачу
$newFileId = 324; //Id нового файла из таблицы b_disk_object
$task = new CTaskItem($taskId, $userId);
$taskData = $task->getData(false);
$task->update(['UF_TASK_WEBDAV_FILES' => array_merge($taskData['UF_TASK_WEBDAV_FILES'], ["n{$newFileId}"])]); Копировать
```

Новинки документации в соцсетях: