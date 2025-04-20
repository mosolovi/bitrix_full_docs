[Бизнес-процессы](/api_help/bizproc/index.php)

[Классы](/api_help/bizproc/bizproc_classes/index.php)

[CBPDocument](/api_help/bizproc/bizproc_classes/CBPDocument/index.php)

GetWorkflowTemplatesForDocumentType

GetWorkflowTemplatesForDocumentType
===================================

```
result_type
public static function GetWorkflowTemplatesForDocumentType(
	array documentType
);Копировать
```

Метод возвращает массив шаблонов рабочих потоков для данного типа документа.

**Примечание:** Метод принимает массив конфигурационных параметров и генерирует скрипты, необходимые для показа файлового диалога. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *documentType* | Код типа документа в виде массива *array(модуль, класс\_документа, код\_типа\_документа\_в\_модуле)* |

#### Возвращаемое значение

Возвращаемый массив имеет вид:

```
array(
	array(
		"ID" => код_шаблона,
		"NAME" => название_шаблона,
		"DESCRIPTION" => описание_шаблона,
		"MODIFIED" => дата_изменения_шаблона,
		"USER_ID" => код_пользователя_изменившего_шаблон,
		"USER_NAME" => имя_пользователя_изменившего_шаблон,
		"AUTO_EXECUTE" => флаг_автовыполнения_CBPDocumentEventType,
		"AUTO_EXECUTE_TEXT" => текст_автовыполнения,
	),
	. . .
)Копировать
```

Новинки документации в соцсетях: