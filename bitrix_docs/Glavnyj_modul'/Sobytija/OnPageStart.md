[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnPageStart (с версии 3.0.6)

OnPageStart
===========

```
функция-обработчик();Копировать
```

Событие "OnPageStart" вызывается в начале выполняемой части пролога сайта, после подключения всех библиотек и отработки [Агентов](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3436).

#### Параметры функции-обработчика

Без параметров.

#### Смотрите также

* [Событие "OnBeforeProlog"](/api_help/main/events/onbeforeprolog.php)
* [Этапы выполнения страницы и доступные на каждом этапе переменные и константы](/api_help/main/general/pageplan.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

#### Пример регистрации функции-обработчика:

```
<?
RegisterModuleDependences("main", "OnPageStart", "statistic", "CStatistic", "Stoplist", "100");
?>Копировать
```

Новинки документации в соцсетях: