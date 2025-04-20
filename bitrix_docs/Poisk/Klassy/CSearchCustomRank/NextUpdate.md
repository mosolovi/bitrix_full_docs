[Поиск](/api_help/search/index.php)

[Классы](/api_help/search/classes/index.php)

[CSearchCustomRank](/api_help/search/classes/csearchcustomrank/index.php)

NextUpdate (доступен с 5.1.1)

NextUpdate
==========

Включить вкладки

Описание и параметры

Смотрите также

### Описание и параметры

```
array
CSearchCustomRank::NextUpdate(
);Копировать
```

Шаг применения изменений правил сортировки. Нестатический метод.

Данный метод применяет следующее непримененное правило сортировки к поисковому индексу. Применение правил требуется всякий раз когда происходят их изменения ([CSearchCustomRank::Add](/api_help/search/classes/csearchcustomrank/add.php), [CSearchCustomRank::Update](/api_help/search/classes/csearchcustomrank/update.php) и [CSearchCustomRank::Delete](/api_help/search/classes/csearchcustomrank/delete.php)). При индексации данных или после переиндексации данная процедура не требуется, т.к. правила сортировки учитываются в процессе построения поискового индекса.

Перед началом применения правил необходимо инициировать процесс вызвав [CSearchCustomRank::StartUpdates](/api_help/search/classes/csearchcustomrank/startupdate.php).

#### Параметры метода

Нет параметров.

#### Возвращаемые значения

В случае успешного выполнения возвращается массив следующей структуры:

* **DONE** - количество уже примененных правил;
* **TODO** - сколько правил еще надо применить.

В противном случае возвращается false и через LAST\_ERROR экземпляра класса можно получить текст сообщения об ошибке.

### Смотрите также

* [CSearchCustomRank::StartUpdates](/api_help/search/classes/csearchcustomrank/startupdate.php)
* [CSearchCustomRank::Add](/api_help/search/classes/csearchcustomrank/add.php)
* [CSearchCustomRank::Update](/api_help/search/classes/csearchcustomrank/update.php)
* [CSearchCustomRank::Delete](/api_help/search/classes/csearchcustomrank/delete.php)

Новинки документации в соцсетях: