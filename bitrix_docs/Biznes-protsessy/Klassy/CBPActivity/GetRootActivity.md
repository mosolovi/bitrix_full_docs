[Бизнес-процессы](/api_help/bizproc/index.php)

[Классы](/api_help/bizproc/bizproc_classes/index.php)

[CBPActivity](/api_help/bizproc/bizproc_classes/CBPActivity/index.php)

GetRootActivity

GetRootActivity
===============

```
CBPActivity
CBPActivity::GetRootActivity(
);Копировать
```

Метод возвращает корневое действие бизнес-процесса. Корневое действие реализует интерфейс **IBPRootActivity**.

#### Возвращаемое значение

Объект типа *CBPActivity*, представляющий корневое действие бизнес-процесса.

#### Примеры использования

```
<?
$rootActivity = $this->GetRootActivity();
$documentId = $rootActivity->GetDocumentId();
?>Копировать
```

Новинки документации в соцсетях: