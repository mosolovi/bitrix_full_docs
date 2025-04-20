[Веб-аналитика](/api_help/statistic/index.php)

[Классы](/api_help/statistic/classes/index.php)

[CStatistics](/api_help/statistic/classes/cstatistics/index.php)

Keep

Keep
====

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
CStatistics::Keep(
	bool handle_call = false
)Копировать
```

Вызов данного метода обеспечивает сбор всех статистических данных.

При инсталлированном модуле статистики данный метод автоматически вызывается в прологе. Но есть возможность отключить автоматический вызов этого метода в прологе, инициализировав константу [STOP\_STATISTICS](/api_help/main/general/constants.php#stop_statistics) перед подключением пролога. После этого данный метод можно вызвать, указав в параметрах *handle\_call*=true.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *handle\_call* | Если значение данного параметра равно "true", то метод проигнорирует константу [STOP\_STATISTICS](/api_help/main/general/constants.php#stop_statistics) и продолжит свою работу. |

#### Смотрите также

* [Константа "STOP\_STATISTICS"](/api_help/main/general/constants.php#stop_statistics)
* [Константа "NO\_KEEP\_STATISTIC"](/api_help/main/general/constants.php#no_keep_statistic)

### Примеры использования

```
<?
// отключим автоматический сбор статистики в прологе
define("STOP_STATISTICS", true);
require($_SERVER["DOCUMENT_ROOT"]."/bitrix/header.php");
// вручную запустим сбор статистики
CStatistics::Keep(true);
...
?>Копировать
```

Новинки документации в соцсетях: