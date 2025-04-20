[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTaskFilterCtrl](/api_help/tasks/classes/ctaskfilterctrl/index.php)

GetInstance (12.0.1)

GetInstance
===========

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
object
CTaskFilterCtrl::getInstance(
	$userId,
	$bGroupMode = false
);
Копировать
```

Метод возвращает экземпляр класса **CTaskFilterCtrl**.

**Примечание:** Метод принимает массив конфигурационных параметров и генерирует скрипты, необходимые для показа файлового диалога. Метод статический.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| *$userId* | Идентификатор пользователя, от имени которого ведется работа (для возможности имперсонализации). |  |
| *$bGroupMode* | Флаг "режима группы". При включенном режиме (**true**) возвращается другой набор предустановленных фильтров.  По умолчанию — **false**. | 12.5.0 |

#### Возвращаемое значение

Возвращает объект класса **CTaskFilterCtrl**. При повторном вызове метода с параметрами, которые уже были переданы ранее, будет возвращен один и тот же объект.

### Примеры использования

```
<?php
CModule::IncludeModule('tasks');
$userId = (int) $GLOBALS['USER']->getId();
$bGroupMode = false;
$oFilter1 = CTaskFilterCtrl::getInstance($userId, $bGroupMode);
$bGroupMode = true;
$oFilter2 = CTaskFilterCtrl::getInstance($userId, $bGroupMode);
$oFilter3 = CTaskFilterCtrl::getInstance($userId, $bGroupMode);
var_dump ($oFilter1 === $oFilter2);	// выведет false
// выведет true, т.к. в обеих переменных ссылка на один и тот же объект
var_dump ($oFilter2 === $oFilter3);
?>
Копировать
```

Новинки документации в соцсетях: