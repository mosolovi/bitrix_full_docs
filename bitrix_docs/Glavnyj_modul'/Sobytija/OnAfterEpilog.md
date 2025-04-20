[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnAfterEpilog (с версии 3.0.11)

OnAfterEpilog
=============

```
функция-обработчик();Копировать
```

Событие "OnAfterEpilog" возникает в конце выполняемой части эпилога сайта (после события [OnEpilog](/api_help/main/events/onepilog.php)).

#### Параметры функции-обработчика

Без параметров.

#### Смотрите также

* [Событие "OnEpilog"](/api_help/main/events/onepilog.php)
* [Этапы выполнения страницы и доступные на каждом этапе переменные и константы](/api_help/main/general/pageplan.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

#### Пример регистрации функции-обработчика:

```
<?
RegisterModuleDependences(
	"main", 
	"OnAfterEpilog", 
	"compression",
	"CCompress",
	"OnAfterEpilog"
);
?>Копировать
```

Новинки документации в соцсетях: