[Бизнес-процессы](/api_help/bizproc/index.php)

[Классы](/api_help/bizproc/bizproc_classes/index.php)

[CBPRuntime](/api_help/bizproc/bizproc_classes/CBPRuntime/index.php)

StartRuntime

StartRuntime
============

```
public int 
CBPRuntime::StartRuntime( void );Копировать
```

Метод запускает исполняющую среду. Исполняющая среда должна быть запущена перед любым ее использованием.

**Примечание**: некоторые методы автоматически запускают окружающую среду. При этом повторный запуск исполняющей среды безопасен.

#### 

#### Примеры использования

```
<?
$runtime = CBPRuntime::GetRuntime();
$runtime->StartRuntime();
$documentService = $runtime->GetService("DocumentService");
$arDocumentFields = $documentService->GetDocumentFields($documentType);
foreach ($arDocumentFields as $key => $value)
	$arSelectFields[] = $key;
?>Копировать
```

Новинки документации в соцсетях: