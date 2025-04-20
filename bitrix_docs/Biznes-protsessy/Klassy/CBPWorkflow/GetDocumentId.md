[Бизнес-процессы](/api_help/bizproc/index.php)

[Классы](/api_help/bizproc/bizproc_classes/index.php)

[CBPWorkflow](/api_help/bizproc/bizproc_classes/CBPWorkflow/index.php)

GetDocumentId

GetDocumentId
=============

```
array
public function GetDocumentId()Копировать
```

Метод возвращает идентификатор документа, над которым запущен бизнес-процесс.

#### Возвращаемое значение

Возвращается идентификатор документа, который представляет собой массив из трех элементов: *array(код\_модуля, класс\_документа, код\_документа)*.

```
Array
	(
		[0] => crm
		[1] => CCrmDocumentLead
		[2] => LEAD_1261807
	)Копировать
```

Новинки документации в соцсетях: