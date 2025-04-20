[Бизнес-процессы](/api_help/bizproc/index.php)

[Классы](/api_help/bizproc/bizproc_classes/index.php)

[CBPDocument](/api_help/bizproc/bizproc_classes/CBPDocument/index.php)

StartWorkflow

StartWorkflow
=============

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
string
public static function CBPDocument::StartWorkflow(
	integer workflowTemplateId,
	array documentId,
	array arParameters,
	array &arErrors
);Копировать
```

Метод запускает рабочий поток по коду его шаблона. Это рекомендуемый метод для запуска бизнес-процессов.

**Примечание:** Метод принимает массив конфигурационных параметров и генерирует скрипты, необходимые для показа файлового диалога. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *workflowTemplateId* | Код шаблона рабочего потока. |
| *documentId* | Массив из 3 элементов. id модуля, сущность (класс) и непосредственно ID документа, например:  ``` ['crm', 'CCrmDocumentLead', 'LEAD_1'] ['lists', 'BizprocDocument', '22'] ['disk', 'Bitrix\Disk\BizProcDocument', '490'] ['tasks', 'Bitrix\Tasks\Integration\Bizproc\Document\Task', '13']Копировать ```   Для бизнес-процессов:   ``` $documentId => array('lists', 'BizprocDocument', $id_element)Копировать ```   Для шаблона списка:   ``` $documentId => array('lists', 'Bitrix\Lists\BizprocDocumentLists', $id_element)Копировать ``` |
| *arParameters* | Массив параметров запуска рабочего потока.   **Примечание**: если процесс запускается из другого процесса через API, и при этом передается значение множественного параметра, то оно должно передаваться в виде массива. |
| *arErrors* | Массив ошибок, которые произошли при запуске рабочего потока в виде  ``` array( 	array( 		"code" => код_ошибки, 		"message" => сообщение, 		"file" => путь_к_файлу 	), 	... ) Копировать ``` |

#### Возвращаемое значение

Возвращается идентификатор запущенного бизнес-процесса. В случае ошибки заполняется массив ошибок.

### Смотрите также

* [CBPRuntime::CreateWorkflow](/api_help/bizproc/bizproc_classes/CBPRuntime/CreateWorkflow.php)

### Примеры использования

```
<?
// Запустим бизнес-процесс по шаблону $workflowTemplateId с входящими параметрами $arWorkflowParameters
// для документа array("bizproc", "CBPVirtualDocument", $documentId)
$arErrorsTmp = array();
$wfId = CBPDocument::StartWorkflow(
	$workflowTemplateId,
	array("bizproc", "CBPVirtualDocument", $documentId),
	array_merge($arWorkflowParameters, array("TargetUser" => "user_".intval($GLOBALS["USER"]->GetID()))),
	$arErrorsTmp
);
if (count($arErrorsTmp) > 0)
{
	foreach ($arErrorsTmp as $e)
		$errorMessage .= "[".$e["code"]."] ".$e["message"]."
";
}
?>Копировать
```

Новинки документации в соцсетях: