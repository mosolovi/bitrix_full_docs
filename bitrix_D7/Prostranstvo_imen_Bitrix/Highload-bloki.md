[Пространство имён Bitrix](/api_d7/bitrix/index.php)

Highload-блоки

Highload-блоки
==============

`\Bitrix\Highloadblock` - пространство имен модуля **Highload-блоки**.

Перед использованием модуля необходимо проверить установлен ли он, и подключить его при помощи конструкции:

```
\Bitrix\Main\Loader::includeModule('highloadblock');
Копировать
```

| Класс | Описание |
| --- | --- |
| [DataManager](/api_d7/bitrix/highloadblock/datamanager/index.php) | Класс для работы с данными highload-блоков. |
| [HighloadBlockLangTable](/api_d7/bitrix/highloadblock/highloadblocklangtable/index.php) | Класс для работы с таблицей языкозависимых параметров highload-блоков. |
| [HighloadBlockRightsTable](/api_d7/bitrix/highloadblock/highloadblockrightstable/index.php) | Класс для работы с таблицей прав к highload-блокам. |
| [HighloadBlockTable](/api_d7/bitrix/highloadblock/highloadblocktable/index.php) | Класс для работы с таблицей highload-блоков. |

**Важно!** Нельзя вызывать highloadblock до обработчика пользовательских свойств.

Новинки документации в соцсетях: