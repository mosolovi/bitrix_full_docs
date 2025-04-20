[Бизнес-процессы](/api_help/bizproc/index.php)

[Классы](/api_help/bizproc/bizproc_classes/index.php)

[CBPDocument](/api_help/bizproc/bizproc_classes/CBPDocument/index.php)

AutoStartWorkflows

AutoStartWorkflows
==================

Включить вкладки

Описание и параметры

Смотрите также

### Описание и параметры

```
void
public static function CBPDocument::AutoStartWorkflows(
	array documentType,
	integer autoExecute,
	array documentId,
	array arParameters,
	array &arErrors
);Копировать
```

Метод запускает рабочие потоки, настроенные на автозапуск.

**Примечание:** Метод принимает массив конфигурационных параметров и генерирует скрипты, необходимые для показа файлового диалога. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *documentType* | Код типа документа в виде массива *array(модуль, класс\_документа, код\_типа\_документа\_в\_модуле)* |
| *autoExecute* | Флаг **CBPDocumentEventType** типа автозапуска (1 = CBPDocumentEventType::Create, 2 = CBPDocumentEventType::Edit) |
| *documentId* | Код документа в виде массива *array(модуль, класс\_документа, код\_документа\_в\_модуле)* |
| *arParameters* | Массив параметров запуска рабочего потока |
| *arErrors* | Массив ошибок, которые произошли при запуске рабочего потока в виде  ``` array( 	array( 		"code" => код_ошибки, 		"message" => сообщение, 		"file" => путь_к_файлу 	), 	... )Копировать ``` |

### Смотрите также

* [CBPDocument::StartWorkflow](/api_help/bizproc/bizproc_classes/CBPDocument/StartWorkflow.php)

Новинки документации в соцсетях: