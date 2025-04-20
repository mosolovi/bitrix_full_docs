[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnBeforeProlog (с версии 3.0.6)

OnBeforeProlog
==============

```
функция-обработчик();Копировать
```

Событие "OnBeforeProlog" вызывается в выполняемой части пролога сайта (после события [OnPageStart](/api_help/main/events/onpagestart.php)).

#### Параметры функции-обработчика

Без параметров.

#### Смотрите также

* [Событие "OnPageStart"](/api_help/main/events/onpagestart.php)
* [Этапы выполнения страницы и доступные на каждом этапе переменные и константы](/api_help/main/general/pageplan.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

#### Пример:

```
<?
// файл /bitrix/php_interface/init.php
AddEventHandler("main", "OnBeforeProlog", "MyOnBeforePrologHandler", 50);
public static function MyOnBeforePrologHandler()
{
	global $USER;
	if(SITE_TEMPLATE_ID=='mynewtemplate' && $_SERVER['REMOTE_ADDR']!='127.0.0.1' && !$USER->IsAdmin())
		die('This template temporary unavailable.');
}
?>Копировать
```

Новинки документации в соцсетях: