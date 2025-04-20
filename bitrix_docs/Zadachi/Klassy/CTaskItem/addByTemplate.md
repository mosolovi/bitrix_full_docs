[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskItem](/api_help/tasks/classes/ctaskitem/index.php)

addByTemplate (С версии 14.5.11)

addByTemplate
=============

Включить вкладки

Описание и параметры

Пример использования

### Описание и параметры

```
CTaskItem[]
CTaskItem::addByTemplate(
	$templateId, 
	$executiveUserId,
	$overrideTaskData = array(), 
	$parameters = array() 
)Копировать
```

Метод добавляет задачу по шаблону.

#### Возвращаемое значение

Данный метод возвращает массив созданных экземпляров класса [CTaskItem](/api_help/tasks/classes/ctaskitem/index.php).

**Примечание:** Метод принимает массив конфигурационных параметров и генерирует скрипты, необходимые для показа файлового диалога. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *$templateId* | ID шаблона. |
| *$executiveUserId* | ID исполнителя задачи. |
| *$overrideTaskData* | Массив переопределяемых в задаче полей. |
| *$parameters* | Массив параметров шаблона. |

### Пример использования

```
CModule::IncludeMOdule('tasks');
$res = CTaskItem::addByTemplate(50, 1, false);
foreach($res as $taskInst)
{
	$data = $taskInst->getData(false);
	print($data['ID'].' -> '.$data['TITLE'].PHP_EOL);
}Копировать
```

Новинки документации в соцсетях: