[Бизнес-процессы](/api_help/bizproc/index.php)

[Классы](/api_help/bizproc/bizproc_classes/index.php)

CBPActivity (С версии 8.5.3)

CBPActivity
===========

Включить вкладки

Описание

Список методов

Пример

### Описание

Все, что происходит в бизнес-процессе — это действия. Сам бизнес-процесс представляет собой составное действие, которое позволяет определять внутри себя дочерние действия. Действие в бизнес-процессе имеет уникальное в рамках этого бизнес-процесса имя.

Действие — это класс, который наследуется от абстрактного класса **CBPActivity** или его потомков. Название класса должно начинаться с подстроки "CBP" и может состоять из латинских букв и цифр.

```
<?
if (!defined("B_PROLOG_INCLUDED") || B_PROLOG_INCLUDED!==true)die();
class CBPMyActivity1
	extends CBPActivity
{
	. . .
}
?>
Копировать
```

Непосредственно от абстрактного класса CBPActivity наследуются действия, которые не могут содержать внутри себя другие действия. Этот класс определяет набор базовых методов, которые необходимы любому действию. Некоторые методы, определенные в классе CBPActivity могут или должны быть переопределены в классе-наследнике.

Составные действия наследуются от абстрактного класса **CBPCompositeActivity**, который в свою очередь наследуется от класса CBPActivity. Класс **CBPCompositeActivity** обеспечивает поддержку возможности включать внутрь действия дочерние действия. Например, составным действием является стандартное действие **CBPParallelActivity** (параллельное выполнение), которое содержит в себе дочерние действия, соответствующие веткам параллельного выполнения.

Класс **CBPCompositeActivity** содержит член **arActivities**, с помощью которого можно обращаться к дочерним действиям.

Класс **CBPActivity** содержит следующие члены, которые можно применять в действиях-наследниках:

* **workflow** – содержит объект-оболочку типа CBPWorkflow для данного бизнес-процесса,
* **parent** – содержит родительское действие,
* **executionStatus** – статус выполнения действия,
* **executionResult** – результат выполнения действия.

### Список методов

| Метод | Описание | **С версии** |
| --- | --- | --- |
| [Execute](/api_help/bizproc/bizproc_classes/CBPActivity/Execute.php) | Этот метод вызывается исполняющей средой при выполнении действия. Он непосредственно реализует поведение действия и должен быть переопределен в каждом действии. |  |
| [Initialize](/api_help/bizproc/bizproc_classes/CBPActivity/Initialize.php) | Этот метод вызывается исполняющей средой для инициализации действия, которая происходит до запуска бизнес-процесса на выполнение. Большинство действий не переопределяют этот метод. |  |
| [HandleFault](/api_help/bizproc/bizproc_classes/CBPActivity/HandleFault.php) | Этот метод вызывается исполняющей средой при возникновении ошибки выполнения действия. Метод может быть переопределен, если при возникновении ошибки выполнения действия необходимо выполнить какой-либо код. |  |
| [AddStatusChangeHandler](/api_help/bizproc/bizproc_classes/CBPActivity/AddStatusChangeHandler.php) | Метод добавляет новый обработчик события изменения статуса действия. |  |
| [GetName](/api_help/bizproc/bizproc_classes/CBPActivity/GetName.php) | Метод возвращает имя действия. Имя действия уникально в рамках бизнес-процесса. |  |
| [GetRootActivity](/api_help/bizproc/bizproc_classes/CBPActivity/GetRootActivity.php) | Метод возвращает корневое действие бизнес-процесса. Корневое действие реализует интерфейс IBPRootActivity. |  |
| [GetWorkflowInstanceId](/api_help/bizproc/bizproc_classes/CBPActivity/GetWorkflowInstanceId.php) | Метод возвращает код бизнес-процесса. |  |
| [RemoveStatusChangeHandler](/api_help/bizproc/bizproc_classes/CBPActivity/RemoveStatusChangeHandler.php) | Метод удаляет обработчик события изменения статуса действия. |  |
| [WriteToTrackingService](/api_help/bizproc/bizproc_classes/CBPActivity/WriteToTrackingService.php) | Метод записывает в лог произвольное сообщение. Кроме того может быть записано, от имени какого пользователя отправляется это сообщение. |  |

### Пример

```
<?
// Код класса действия, которое создаст файл с указанным в свойствах действия именем
class CBPMyActivity
	extends CBPActivity
{
	public function __construct($name)
	{
		parent::__construct($name);
		// Определим свойство FileName, в котором будет содержаться имя файла
		$this->arProperties = array("Title" => "", "FileName" => "");
	}
	// Исполняемый метод действия
	public function Execute()
	{
		// Если свойство с именем файла задано, осуществим в него запись
		// Обратите внимание, что для упрощения кода здесь не добавлены
		// необходимые проверки безопасности 
		if (strlen($this->FileName) > 0)
		{
			$f = fopen($this->FileName, "w");
			fwrite($f, "Какой-то текст");
			fclose($f);
		}
		// Вернем указание исполняющей среде, что действие завершено
		return CBPActivityExecutionStatus::Closed;
	}
}
?>Копировать
```

Новинки документации в соцсетях: