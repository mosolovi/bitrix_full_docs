[Бизнес-процессы](/api_help/bizproc/index.php)

[Классы](/api_help/bizproc/bizproc_classes/index.php)

[CBPDocument](/api_help/bizproc/bizproc_classes/CBPDocument/index.php)

DeleteWorkflowTemplate

DeleteWorkflowTemplate
======================

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
void
CBPDocument::DeleteWorkflowTemplate(
	int id,
	array documentType,
	array &arErrors
);Копировать
```

Метод удаляет шаблон бизнес-процесса.

**Примечание:** Метод принимает массив конфигурационных параметров и генерирует скрипты, необходимые для показа файлового диалога. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *id* | Код шаблона бизнес-процесса |
| *documentType* | Код типа документа в виде массива *array(модуль, класс\_документа, код\_типа\_документа\_в\_модуле)* |
| *arErrors* | массив ошибок, которые произошли при выполнении в виде  ``` array( 	array( 		"code" => код_ошибки, 		"message" => сообщение, 		"file" => путь_к_файлу 	), 	... )Копировать ``` |

### Примеры использования

```
<?
// Удалим шаблон бизнес-процесса с кодом 132 для инфоблока 18
CBPDocument::DeleteWorkflowTemplate(
	132,
	array("iblock", "CIBlockDocument", "iblock_18"),
	$arErrorTmp
);
?>Копировать
```

Новинки документации в соцсетях: