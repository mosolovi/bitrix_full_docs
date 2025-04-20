[Бизнес-процессы](/api_help/bizproc/index.php)

[Классы](/api_help/bizproc/bizproc_classes/index.php)

[CBPDocument](/api_help/bizproc/bizproc_classes/CBPDocument/index.php)

UpdateWorkflowTemplate

UpdateWorkflowTemplate
======================

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
void
CBPDocument::UpdateWorkflowTemplate(
	int id,
	array documentType,
	array arFields,
	array& arErrors
);Копировать
```

Метод изменяет параметры шаблона бизнес-процесса.

**Примечание:** Метод принимает массив конфигурационных параметров и генерирует скрипты, необходимые для показа файлового диалога. Метод статичный.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *id* | Код шаблона бизнес-процесса |
| *documentType* | Код типа документа в виде массива *array(модуль, класс\_документа, код\_типа\_документа\_в\_модуле)* |
| *arFields* | Массив новых значений параметров шаблона бизнес-процесса |
| *arErrors* | массив ошибок, которые произошли при выполнении в виде  ``` array( 	array( 		"code" => код_ошибки, 		"message" => сообщение, 		"file" => путь_к_файлу 	), 	... )Копировать ``` |

### Примеры использования

```
<?
// изменим флаг автозапуска шаблона бизнес-процесса с кодом 132 для инфоблока с кодом 32
CBPDocument::UpdateWorkflowTemplate(
	132,
	array("iblock", "CIBlockDocument", "iblock_32"),
	array(
		"AUTO_EXECUTE" => CBPDocumentEventType::Create
	),
	$arErrorsTmp
);
?>Копировать
```

Новинки документации в соцсетях: