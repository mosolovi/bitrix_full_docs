[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskItem](/api_help/tasks/classes/ctaskitem/index.php)

getDescription (12.5.0)

getDescription
==============

```
string
public function getDescription(
	$format = CTaskItem::DESCR_FORMAT_HTML
);
Копировать
```

Данный метод возвращает описание задачи.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *$format* | Допустимые значения:  * **CTaskItem::DESCR\_FORMAT\_HTML** — описание будет возвращено в формате HTML, предварительно будет обработано санитайзером (если это включено в настройках модуля задач); * **CTaskItem::DESCR\_FORMAT\_PLAIN\_TEXT** — описание будет возвращено в виде «плоского» текста (без HTML-тегов); * **CTaskItem::DESCR\_FORMAT\_RAW** — описание будет возвращено в том формате, в котором хранится в БД (HTML, либо BB-code), обработка санитайзером производиться не будет. |

Новинки документации в соцсетях: