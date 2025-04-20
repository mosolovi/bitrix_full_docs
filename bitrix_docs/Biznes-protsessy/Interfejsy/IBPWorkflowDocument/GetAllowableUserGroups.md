[Бизнес-процессы](/api_help/bizproc/index.php)

[Интерфейсы](/api_help/bizproc/interface/index.php)

[IBPWorkflowDocument](/api_help/bizproc/interface/IBPWorkflowDocument/index.php)

GetAllowableUserGroups

GetAllowableUserGroups
======================

```
array
IBPWorkflowDocument::GetAllowableUserGroups(
	mixed documentType
);Копировать
```

Метод для типа документа возвращает массив возможных групп пользователей в виде

```
array(
	"код_группы" => "название_группы_на_текущем_языке",
	. . .
)Копировать
```

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *documentType* | Код типа документа |

Новинки документации в соцсетях: