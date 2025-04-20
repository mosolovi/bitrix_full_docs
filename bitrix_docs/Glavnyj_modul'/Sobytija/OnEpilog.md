[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnEpilog (с версии 3.3.21)

OnEpilog
========

```
функция-обработчик();Копировать
```

Событие "OnEpilog" вызывается в конце визуальной части эпилога сайта.

#### Параметры функции-обработчика

Без параметров.

#### Смотрите также

* [Событие "OnAfterEpilog"](/api_help/main/events/onafterepilog.php)
* [Этапы выполнения страницы и доступные на каждом этапе переменные и константы](/api_help/main/general/pageplan.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

#### Пример регистрации функции-обработчика:

```
<?
AddEventHandler("main", "OnEpilog", "statistic", "CStatistic", "Set404", "100");
?>Копировать
```

Новинки документации в соцсетях: