[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskFiles](/api_help/tasks/classes/ctaskfiles/index.php)

IsFileAccessibleByUser (С версии 12.5.0, устарел с версии 16.7.0)

IsFileAccessibleByUser
======================

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
boolean
CTaskFiles::isFileAccessibleByUser(
	$fileId,
	$userId
);
Копировать
```

Метод проверяет доступность файла на чтение (в рамках модуля задач) указанному пользователю.

**Примечание:** Метод принимает массив конфигурационных параметров и генерирует скрипты, необходимые для показа файлового диалога. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *$fileId* | Идентификатор проверяемого файла. |
| *$userId* | Идентификатор пользователя, для которого проверяется доступность файла. |

#### Возвращаемое значение

Возвращает *true*, если файл с идентификатором **$fileId** доступен пользователю с идентификатором **$userId** на чтение в рамках модуля задач. Файл доступен пользователю, если файл прикреплен хотя бы к одной из задач, доступных пользователю, либо хотя бы к одному из шаблонов задач, доступных пользователю. Также, файл доступен, если он был зарегистрирован с помощью **CTaskFiles::saveFileTemporary()** как временный для последующего прикрепления к задаче.
  
Если пользователь с **$userId** является администратором, то будет возвращено *true* независимо от того, имеется ли данный файл в задачах/шаблонах или среди временно загруженных файлов.

### Примеры использования

```
<?php
CModule::IncludeModule('tasks');
$fileId  = 456;
$userId = (int) $GLOBALS['USER']->getId();
if (CTaskFiles::isFileAccessibleByUser($fileId, $userId))
	echo 'Files is accessible';
else
	echo 'Access denied';
?>
Копировать
```

Новинки документации в соцсетях: