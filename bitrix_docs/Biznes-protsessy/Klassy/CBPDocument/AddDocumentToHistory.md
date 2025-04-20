[Бизнес-процессы](/api_help/bizproc/index.php)

[Классы](/api_help/bizproc/bizproc_classes/index.php)

[CBPDocument](/api_help/bizproc/bizproc_classes/CBPDocument/index.php)

AddDocumentToHistory

AddDocumentToHistory
====================

```
integer
public static function CBPDocument::AddDocumentToHistory(
	array documentId,
	string name,
	integer userId
);Копировать
```

Метод добавляет текущую версию документа в историю.

**Примечание:** Метод принимает массив конфигурационных параметров и генерирует скрипты, необходимые для показа файлового диалога. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *documentId* | Идентификатор документа, заданный в виде массива *array(код\_модуля, класс\_документа, идентификатор\_документа\_в\_модуле)* |
| *name* | Название записи в истории |
| *userId* | Идентификатор пользователя, от имени которого заносится запись |

#### Возвращаемое значение

Возвращается идентификатор записи в истории или false в случае ошибки.

Новинки документации в соцсетях: