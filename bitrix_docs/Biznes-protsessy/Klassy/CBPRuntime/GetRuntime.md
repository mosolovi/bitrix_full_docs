[Бизнес-процессы](/api_help/bizproc/index.php)

[Классы](/api_help/bizproc/bizproc_classes/index.php)

[CBPRuntime](/api_help/bizproc/bizproc_classes/CBPRuntime/index.php)

GetRuntime

GetRuntime
==========

```
CBPRuntime
public function CBPRuntime::GetRuntime();Копировать
```

Статический метод возвращает экземпляр класса, представляющего текущую исполняющую среду.

**Примечание**: в рамках хита должен быть только один экземпляр класса исполняющей среды (шаблон **Одиночка**). Этот метод возвращает данный экземпляр.

#### Возвращаемое значение

Возвращается экземпляр класса, представляющего текущую исполняющую среду.

#### Примеры использования

```
<?
$runtime = CBPRuntime::GetRuntime();
$runtime->StartRuntime();
$documentService = $runtime->GetService("DocumentService");
$arDocumentFields = $documentService->GetDocumentFields($documentType);
foreach ($arDocumentFields as $key => $value)
{
	print_r($value);
}
?>Копировать
```

Новинки документации в соцсетях: