[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskElapsedItem](/api_help/tasks/classes/ctaskelapseditem/index.php)

add (12.5.4)

add
===

```
object
CTaskElapsedItem::add(
	object CTaskItemInterface, oTaskItem,
	array arFields = array()
);Копировать
```

Метод добавляет затраченное время к задаче.

**Примечание:** Метод принимает массив конфигурационных параметров и генерирует скрипты, необходимые для показа файлового диалога. Метод статический.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| *oTaskItem* | Объект класса CTaskItem |  |
| *arFields* | Массив, содержащий записи о времени и комментарии (**MINUTES** и **COMMENT\_TEXT**). | До 14.0.10 |
| *arFields* | Массив, содержащий записи о времени и комментарии (**SECONDS**, **COMMENT\_TEXT** и **CREATED\_DATE**). Допустимо использовать **MINUTES** вместо **SECONDS**, но нельзя их использовать одновременно. | с 14.0.10 |

#### Возвращаемое значение

Метод возвращает объект класса **CTaskElapsedItem**.

Новинки документации в соцсетях: