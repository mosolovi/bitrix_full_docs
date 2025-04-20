[Поиск](/api_help/search/index.php)

[Классы](/api_help/search/classes/index.php)

[CSearchCustomRank](/api_help/search/classes/csearchcustomrank/index.php)

StartUpdate (доступен с 5.1.1)

StartUpdate
===========

Включить вкладки

Описание и параметры

Смотрите также

### Описание и параметры

```
CDBResult
CSearchCustomRank::StartUpdate(
);Копировать
```

Подготовка к применению изменений в правилах. Нестатический метод.

Данный метод начинает процедуру применения правил сортировки к поисковому
индексу. Применение правил требуется всякий раз когда происходят их изменения
([CSearchCustomRank::Add](/api_help/search/classes/csearchcustomrank/add.php), [CSearchCustomRank::Update](/api_help/search/classes/csearchcustomrank/update.php) и [CSearchCustomRank::Delete](/api_help/search/classes/csearchcustomrank/delete.php)). При индексации данных или
после переиндексации данная процедура не требуется, т.к. правила сортировки
учитываются в процессе построения поискового индекса.

Фактически данный метод сбрасывает все весовые коэффициенты. А для собственно
применения правил необходимо воспользоваться пошаговой [CSearchCustomRank::NextUpdate](/api_help/search/classes/csearchcustomrank/nextupdate.php).

#### Параметры метода

Нет параметров.

#### Возвращаемые значения

В случае успешного выполнения возвращается объект CDBResult. В противном
случае возвращается false.

### Смотрите также

* [CSearchCustomRank::NextUpdate](/api_help/search/classes/csearchcustomrank/nextupdate.php)
* [CSearchCustomRank::Add](/api_help/search/classes/csearchcustomrank/add.php)
* [CSearchCustomRank::Update](/api_help/search/classes/csearchcustomrank/update.php)
* [CSearchCustomRank::Delete](/api_help/search/classes/csearchcustomrank/delete.php)

Новинки документации в соцсетях: