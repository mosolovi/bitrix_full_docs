[Бизнес-процессы](/api_help/bizproc/index.php)

[Классы](/api_help/bizproc/bizproc_classes/index.php)

[CBPDocument](/api_help/bizproc/bizproc_classes/CBPDocument/index.php)

GetAllowableOperations

GetAllowableOperations
======================

```
array
public static function CBPDocument::GetAllowableOperations(
	integer userId,
	array arGroups,
	array arStates
);Копировать
```

Метод возвращает массив операций, которые указанный пользователь может совершить, если документ находится в указанных состояниях.

**Примечание:** Метод принимает массив конфигурационных параметров и генерирует скрипты, необходимые для показа файлового диалога. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *userId* | Идентификатор пользователя |
| *arGroups* | Массив групп пользователя |
| *arStates* | Массив состояний рабочих потоков документа |

#### Возвращаемое значение

Если среди состояний нет ни одного рабочего потока типа конечных автоматов, то возвращается null. Если пользователь не может выполнить ни одной операции, то возвращается array(). Иначе возвращается массив доступных для пользователя операций в виде

```
array(
	операция,
	...
)Копировать
```

Новинки документации в соцсетях: