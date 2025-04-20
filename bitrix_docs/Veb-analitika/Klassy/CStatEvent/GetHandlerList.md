[Веб-аналитика](/api_help/statistic/index.php)

[Классы](/api_help/statistic/classes/index.php)

[CStatEvent](/api_help/statistic/classes/cstatevent/index.php)

GetHandlerList

GetHandlerList
==============

Включить вкладки

Описание и параметры

Смотрите также

Возвращаемое значение

Примеры использования

### Описание и параметры

```
array
CStatEvent::GetHandlerList(
	array &handlers
)Копировать
```

Возвращает список [обработчиков CSV файлов](/api_help/statistic/terms.php#handler) для вывода его в выпадающем списке с помощью функции [SelectBoxFromArray](/api_help/main/functions/html/selectboxfromarray.php), либо в списке множественного выбора с помощью функции [SelectBoxMFromArray](/api_help/main/functions/html/selectboxmfromarray.php).

Обработчики CSV файлов могут быть как *пользовательские* (путь к ним указывается в параметре "Путь к дополнительным обработчикам при ручной загрузке событий" в настройках модуля "Статистика"), так и *стандартные* - входящие в дистрибутив модуля (хранятся в каталоге **/bitrix/modules/statistic/loading/**).

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *handlers* | Данная переменная после отработки метода будет содержать в себе массив путей относительно корня к *пользовательским* обработчикам. Пример данного массива:  ``` Array ( 	[0] => /bitrix/php_interface/include/statistic/regnow_alawar.php 	[1] => /bitrix/php_interface/include/statistic/regnow_editable.php 	[2] => /bitrix/php_interface/include/statistic/regsoft_editable.php 	[3] => /bitrix/php_interface/include/statistic/shareit_editable.php 	[4] => /bitrix/php_interface/include/statistic/softkey_editable.php )Копировать ``` |

### Смотрите также

* [CStatEvent::Add](/api_help/statistic/classes/cstatevent/add.php)
* [CStatEvent::AddByEvents](/api_help/statistic/classes/cstatevent/addbyevents.php)
* [Загрузка событий](http://www.1c-bitrix.ru/user_help/statistic/events/event_edit.php)
* [Термин "Событие"](/api_help/statistic/terms.php#event)

### Возвращаемое значение

Пример массива, возвращаемого методом:

  

```
Array
(
	[reference] => Array
	(
		[0] => regnow.php
		[1] => regsoft.php
		[2] => shareit_eur.php
		[3] => shareit_usd.php
		[4] => softkey.php
		[5] => [1] regnow_alawar.php
		[6] => [2] regnow_editable.php
		[7] => [3] regsoft_editable.php
		[8] => [4] shareit_editable.php
		[9] => [5] softkey_editable.php
	)
	[reference_id] => Array
	(
		[0] => /bitrix/modules/statistic/loading/regnow.php
		[1] => /bitrix/modules/statistic/loading/regsoft.php
		[2] => /bitrix/modules/statistic/loading/shareit_eur.php
		[3] => /bitrix/modules/statistic/loading/shareit_usd.php
		[4] => /bitrix/modules/statistic/loading/softkey.php
		[5] => /bitrix/php_interface/include/statistic/regnow_alawar.php
		[6] => /bitrix/php_interface/include/statistic/regnow_editable.php
		[7] => /bitrix/php_interface/include/statistic/regsoft_editable.php
		[8] => /bitrix/php_interface/include/statistic/shareit_editable.php
		[9] => /bitrix/php_interface/include/statistic/softkey_editable.php
	)
)Копировать
```

### Примеры использования

```
<?
// получим список доступных обработчиков
$arrHandlers = CStatEvent::GetHandlerList($arUSER_HANDLERS);
// выведем этот список в виде выпадающего списка
echo SelectBoxFromArray("handler", $arrHandlers, $handler, " ");
?>Копировать
```

Новинки документации в соцсетях: