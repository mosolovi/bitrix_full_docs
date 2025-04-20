[Бизнес-процессы](/api_help/bizproc/index.php)

[Классы](/api_help/bizproc/bizproc_classes/index.php)

CBPRuntime (С версии 8.5.4)

CBPRuntime
==========

**CBPRuntime** - класс исполняющей среды. Он создает бизнес-процессы, а так же инфраструктуру для их исполнения.

Исполняющая среда в рамках одного хита существует в единственном экземпляре. Получить экземпляр исполняющей среды можно с помощью кода:

```
$runtime = CBPRuntime::GetRuntime();Копировать
```

#### Методы класса

| Метод | Описание | **С версии** |
| --- | --- | --- |
| [GetRuntime](/api_help/bizproc/bizproc_classes/CBPRuntime/GetRuntime.php) | Статический метод возвращает экземпляр класса, представляющего текущую исполняющую среду. |  |
| [CreateWorkflow](/api_help/bizproc/bizproc_classes/CBPRuntime/CreateWorkflow.php) | Метод создает новый экземпляр бизнес-процесса над указанным документом. |  |
| [GetService](/api_help/bizproc/bizproc_classes/CBPRuntime/GetService.php) | Метод возвращает экземпляр сервиса исполняющей среды по его имени. |  |
| [GetWorkflow](/api_help/bizproc/bizproc_classes/CBPRuntime/GetWorkflow.php) | Метод возвращает экземпляр бизнес-процесса по его идентификатору. |  |
| [SendExternalEvent](/api_help/bizproc/bizproc_classes/CBPRuntime/SendExternalEvent.php) | Статический метод отправляет внешнее событие указанному бизнес-процессу. |  |
| [StartRuntime](/api_help/bizproc/bizproc_classes/CBPRuntime/StartRuntime.php) | Метод запускает исполняющую среду. Исполняющая среда должна быть запущена перед любым ее использованием. |  |

Новинки документации в соцсетях: