[Бизнес-процессы](/api_help/bizproc/index.php)

[Классы](/api_help/bizproc/bizproc_classes/index.php)

[CBPDocument](/api_help/bizproc/bizproc_classes/CBPDocument/index.php)

GetDocumentState

GetDocumentState
================

```
array
public static function CBPDocument::GetDocumentState(
	array documentId,
	string workflowId
);Копировать
```

Метод для данного документа возвращает состояние указанного рабочего потока.

**Примечание:** Метод принимает массив конфигурационных параметров и генерирует скрипты, необходимые для показа файлового диалога. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *documentId* | Идентификатор документа в виде массива *array(модуль, класс\_документа, код\_документа\_в\_модуле)* |
| *workflowId* | Идентификатор рабочего потока |

#### Возвращаемое значение

Результирующий массив аналогичен массиву метода [CBPDocument::GetDocumentStates](/api_help/bizproc/bizproc_classes/CBPDocument/GetDocumentStates.php).

#### Смотрите также

* [CBPDocument::GetDocumentStates](/api_help/bizproc/bizproc_classes/CBPDocument/GetDocumentStates.php)

Новинки документации в соцсетях: