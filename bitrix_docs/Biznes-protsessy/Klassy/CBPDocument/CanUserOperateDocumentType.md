[Бизнес-процессы](/api_help/bizproc/index.php)

[Классы](/api_help/bizproc/bizproc_classes/index.php)

[CBPDocument](/api_help/bizproc/bizproc_classes/CBPDocument/index.php)

CanUserOperateDocumentType

CanUserOperateDocumentType
==========================

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
bool
public static function CBPDocument::CanUserOperateDocumentType(
	int operation,
	int userId,
	array documentType,
	array arParameters = array()
);Копировать
```

Метод проверяет путем обращения к сущности типа документа, может ли пользователь совершать указанную операцию с документами данного типа.

**Примечание:** Метод принимает массив конфигурационных параметров и генерирует скрипты, необходимые для показа файлового диалога. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| operation | Операция из **CBPCanUserOperateOperation** |
| *userId* | Код пользователя |
| documentType | Код типа документа в виде массива *array(модуль, класс\_документа, код\_типа\_документа\_в\_модуле)* |
| *arParameters* | Ассоциативный массив вспомогательных параметров. Используется для того, чтобы не рассчитывать заново те вычисляемые значения, которые уже известны на момент вызова метода. Стандартными являются ключи массива **DocumentStates** - массив состояний рабочих потоков данного документа, **WorkflowId** - код рабочего потока (если требуется проверить операцию на одном рабочем потоке). Массив может быть дополнен другими произвольными ключами. |

#### Возвращаемое значение

Возвращается true, если пользователь имеет право на выполнение указанной операции. Иначе возвращается false.

### Смотрите также

* [CBPDocument::CanUserOperateDocument](/api_help/bizproc/bizproc_classes/CBPDocument/CanUserOperateDocument.php)

### Примеры использования

```
<?
$bCanAccess = CBPDocument::CanUserOperateDocumentType(
	CBPCanUserOperateOperation::CreateWorkflow,
	$GLOBALS["USER"]->GetID(),
	$documentType,
	array("UserGroups" => $arUserGroups)
);
if (!$bCanAccess)
	die("Access denied");
?>Копировать
```

Новинки документации в соцсетях: