[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskItem](/api_help/tasks/classes/ctaskitem/index.php)

Класс CTaskItem (С версии 12.5.0)

Класс CTaskItem
===============

Включить вкладки

Описание

Список методов

### Описание

**CTaskItem** — высокоуровневое API для работы с отдельными задачами (включает в себя бизнес-логику).

Следует использовать вместо вызовов **CTasks::Update()**, **CTasks::Delete()** и т.д.;

* позволяет вести работу с задачей от имени заданного (не обязательно текущего авторизованного) пользователя;
* обладает внутренним механизмом прозрачного кэширования (не нужно следить за актуализацией кэша при работе с задачей через этот класс — при условии инстанцирования через **getInstance()**);
* применяется блочная «ленивая» подгрузка данных, что благоприятно сказывается на производительности;

Для работы с классом нужно его инстанцировать для конкретной задачи в контексте прав определенного пользователя.

Не является мультитоном, однако рекомендуется инстанцировать экземпляр класс с помощью статического метода **getInstance()**, т. к. в таком случае будет автоматически поддерживаться актуальность кэша.

Например,

```
<?
$taskId = 7;
$userId = $USER->getId();
$oTask = CTaskItem::getInstance($taskId, $userId);
?>Копировать
```

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *$taskId* | идентификатор задачи. |
| *$userId* | идентификатор пользователя, от имени которого ведется работа (для возможности имперсонализации). |

#### Возвращаемое значение

Объект класса CTaskItem. При повторном вызове метода с параметрами, которые уже были переданы ранее, будет возвращен один и тот же объект.

```
array
public function getManifest();
Копировать
```

Возвращает массив с описанием класса.

**Внимание!** Формат массива может произвольно меняться в будущем, он не предназначен для автоматической обработки, однако может быть очень удобен в процессе разработки, т. к. содержит, к примеру, список методов доступных в REST, принимаемые ими значения и т.д.

### Список методов

| Метод | Описание | С версии |
| --- | --- | --- |
| [add](/api_help/tasks/classes/ctaskitem/add.php) | Метод возвращает экземпляр класса CTaskItem. | 12.5.3 |
| [getData](/api_help/tasks/classes/ctaskitem/getdata.php) | Метод возвращает массив, содержащий данные о задаче. | 12.5.4 |
| [getDescription](/api_help/tasks/classes/ctaskitem/getdescription.php) | Метод возвращает описание задачи. |  |
| [getFiles](/api_help/tasks/classes/ctaskitem/getfiles.php) | Метод возвращает массив, содержащий идентификаторы файлов, прикрепленных к задаче. | 12.5.4 |
| [getTags](/api_help/tasks/classes/ctaskitem/gettags.php) | Метод возвращает массив, содержащий теги заданного пользователя в задаче. | 12.5.4 |
| [getDependsOn](/api_help/tasks/classes/ctaskitem/getdependson.php) | Метод возвращает массив, содержащий идентификаторы задач, от которых зависит задача. | 12.5.4 |
| [getAllowedActions](/api_help/tasks/classes/ctaskitem/getallowedactions.php) | Метод возвращает массив, описывающий допустимые действия над задачей. | 12.5.8 |
| [isActionAllowed](/api_help/tasks/classes/ctaskitem/isactionallowed.php) | Метод проверяет разрешено ли действие. |  |
| [delete](/api_help/tasks/classes/ctaskitem/delete.php) | Метод удаляет задачу. | 12.5.3 |
| [delegate](/api_help/tasks/classes/ctaskitem/delegate.php) | Метод делегируюет задачу пользователю. |  |
| [startExecution](/api_help/tasks/classes/ctaskitem/startexecution.php) | Метод переводит задачу в статус «выполняется». |  |
| [defer](/api_help/tasks/classes/ctaskitem/defer.php) | Метод переводит задачу в статус «отложена». |  |
| [renew](/api_help/tasks/classes/ctaskitem/renew.php) | Метод переводит задачу в статус «не выполняется». |  |
| [complete](/api_help/tasks/classes/ctaskitem/complete.php) | Метод переводит задачу в статус «завершена» или «условно завершена (ждет контроля исполнителя)». |  |
| [approve](/api_help/tasks/classes/ctaskitem/approve.php) | Метод переводит задачу, ожидающую контроля, в статус «завершена». |  |
| [disapprove](/api_help/tasks/classes/ctaskitem/disapprove.php) | Метод переводит задачу, ожидающую контроля, в статус «не выполняется». |  |
| [update](/api_help/tasks/classes/ctaskitem/update.php) | Метод изменяет параметры задачи. | 12.5.3 |
| [addByTemplate](/api_help/tasks/classes/ctaskitem/addbytemplate.php) | Метод добавляет задачу по шаблону. | 14.5.11 |
| [addChildTaskByTemplate](/api_help/tasks/classes/ctaskitem/addchildtaskbytemplate.php) | Метод добавляет подзадачи из шаблона. | 14.5.11 |
| [duplicate](/api_help/tasks/classes/ctaskitem/duplicate.php) | Метод копирует задачу или задачи. | 14.5.11 |
| [duplicateChildTasks](/api_help/tasks/classes/ctaskitem/duplicatechildtasks.php) | Метод копирует подзадачи выбранной задачи. | 14.5.11 |
| [addToFavorite](/api_help/tasks/classes/ctaskitem/addtofavorite.php) | Метод добавляет задачу в Избранное. | 15.6.0 |
| [deleteFromFavorite](/api_help/tasks/classes/ctaskitem/deletefromfavorite.php) | Метод удаляет задачу из Избранного. | 15.6.0 |
| [toggleFavorite](/api_help/tasks/classes/ctaskitem/togglefavorite.php) | Меняет для указанной задачи состояние избранности. | 15.6.0 |
| [addProjectDependence](/api_help/tasks/classes/ctaskitem/addprojectedendence.php) | Добавляет зависимость одной задачи от другой в рамках Ганта. |  |
| [updateProjectDependence](/api_help/tasks/classes/ctaskitem/updateprojectdependence.php) | Обновляет зависимость одной задачи от другой в рамках Ганта. | 15.6.0 |

Новинки документации в соцсетях: