[Бизнес-процессы](/api_help/bizproc/index.php)

[Интерфейсы](/api_help/bizproc/interface/index.php)

[IBPWorkflowDocument](/api_help/bizproc/interface/IBPWorkflowDocument/index.php)

GetAllowableOperations

GetAllowableOperations
======================

```
array
IBPWorkflowDocument::GetAllowableOperations(
	mixed documentType
);Копировать
```

Метод для типа документа возвращает массив доступных операций в виде

```
array(
	"код_операции" => "название_операции_на_текущем_языке",
	. . .
)Копировать
```

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *documentType* | Код типа документа |

Новинки документации в соцсетях: