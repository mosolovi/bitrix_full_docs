[Бизнес-процессы](/api_help/bizproc/index.php)

[Классы](/api_help/bizproc/bizproc_classes/index.php)

[CBPRuntime](/api_help/bizproc/bizproc_classes/CBPRuntime/index.php)

CreateWorkflow

CreateWorkflow
==============

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
CBPWorkflow
public function CBPRuntime::CreateWorkflow(
	int workflowTemplateId,
	array documentId,
	array workflowParameters = array()
);Копировать
```

Метод создает новый экземпляр бизнес-процесса над указанным документом. Экземпляр бизнес-процесса создается на основании шаблона бизнес-процесса. Метод при необходимости автоматически запускает исполняющую среду.

Это низкоуровневый метод. Рекомендуется использовать метод [CBPDocument::StartWorkflow](/api_help/bizproc/bizproc_classes/CBPDocument/StartWorkflow.php).

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *workflowTemplateId* | Код шаблона бизнес-процесса |
| *documentId* | Код документа, над которым запускается бизнес-процесс. Имеет вид массива *array(код\_модуля\_документа, класс\_документа, код\_документа)* |
| *workflowParameters* | Массив параметров запуска бизнес-процесса |

#### Возвращаемое значение

Возвращается запущенный экземпляр бизнес-процесса.

#### Исключения

| Код | Описание |
| --- | --- |
| *workflowTemplateId* | Не указан код шаблона бизнес-процесса |
| *EmptyRootActivity* | Не удалось создать экземпляр бизнес-процесса |

### Смотрите также

* [CDBResult](/api_help/main/reference/cdbresult/index.php)

### Примеры использования

```
<?
$runtime = CBPRuntime::GetRuntime();
try
{
	$wi = $runtime->CreateWorkflow($workflowTemplateId, $documentId, $arParameters);
	$wi->Start();
}
catch (Exception $e)
{
	// 
}
?>Копировать
```

Новинки документации в соцсетях: