[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnProlog (с версии 4.0.14)

OnProlog
========

```
функция-обработчик();Копировать
```

Событие "OnProlog"
вызывается в начале визуальной части пролога сайта.

#### Параметры функции-обработчика

Без параметров.

#### Смотрите также

* [Событие "OnBeforeProlog"](/api_help/main/events/onbeforeprolog.php)
* [Этапы выполнения страницы и доступные на каждом этапе переменные и константы](/api_help/main/general/pageplan.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

#### Пример регистрации функции-обработчика:

```
<?
	RegisterModuleDependences(
		"main", 
		"OnProlog",
		"statistic",
		"CStatistic",
		"StartBuffer", 
		"100"
	);
?>Копировать
```

Новинки документации в соцсетях: