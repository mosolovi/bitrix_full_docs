[Подписка, рассылки](/api_help/subscribe/index.php)

[Классы](/api_help/subscribe/classes/index.php)

[CPostingTemplate](/api_help/subscribe/classes/cpostingtemplate/index.php)

Execute (доступен с 4.0.5)

Execute
=======

```
string
CPostingTemplate::Execute();Копировать
```

Метод выбирает шаблон для генерации выпуска рассылки в соответствии с расписанием.

Сначала делается выборка всех рассылок отмеченных как активные и автоматические. Затем для каждой из них выполняется проверка на необходимость генерации выпуска. Как только найдена такая рассылка для нее вызывается метод CPostingTemplate::AddPosting и на этом функция Execute завершает свою работу.

Этот метод предназначен для вызова из сценария cron'а или агента. Метод статический.

#### Параметры

Метод не имеет параметров.

#### Возвращаемые значения

Если была найдена хотя бы одна активная и автоматическая рассылка, то возвращается строка для вызова из агента, иначе возвращается пустая строка.

#### Пример использования в сценарии PHP для cron'а

```
#!/usr/bin/php
<?php
//Здесь необходимо указать ваш DOCUMENT_ROOT!
$_SERVER["DOCUMENT_ROOT"] = "/opt/www/html";
$DOCUMENT_ROOT = $_SERVER["DOCUMENT_ROOT"];
define("NO_KEEP_STATISTIC", true);
define("NOT_CHECK_PERMISSIONS", true);
set_time_limit(0);
define("LANG", "ru");
require($_SERVER["DOCUMENT_ROOT"]."/bitrix/modules/main/include/prolog_before.php");
if (CModule::IncludeModule("subscribe"))
	CPostingTemplate::Execute();
require($_SERVER["DOCUMENT_ROOT"]."/bitrix/modules/main/include/epilog_after.php");
?>Копировать
```

Новинки документации в соцсетях: