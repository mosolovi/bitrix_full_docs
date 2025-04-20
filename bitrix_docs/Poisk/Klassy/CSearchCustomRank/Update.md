[Поиск](/api_help/search/index.php)

[Классы](/api_help/search/classes/index.php)

[CSearchCustomRank](/api_help/search/classes/csearchcustomrank/index.php)

Update (доступен с 5.1.1)

Update
======

Включить вкладки

Описание и параметры

Смотрите также

### Описание и параметры

```
bool
CSearchCustomRank::Update(
	int ID,
	array arFields
);Копировать
```

Изменение правила сортировки. Нестатический метод.

После удаления всех требуемых правил необходимо пересчитать поисковый индекс методами [CSearchCustomRank::StartUpdate](/api_help/search/classes/csearchcustomrank/startupdate.php) и
[CSearchCustomRank::NextUpdate](/api_help/search/classes/csearchcustomrank/nextupdate.php).

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор правила. |
| arFields | Массив со значениями полей [объекта правила сортировки](/api_help/search/classes/csearchcustomrank/fields.php). |

#### Возвращаемые значения

В случае успешного добавления возвращается true. В противном случает возвращается false.

### Смотрите также

* [Поля объекта правила сортировки](/api_help/search/classes/csearchcustomrank/fields.php)
* [CSearchCustomRank::StartUpdate](/api_help/search/classes/csearchcustomrank/startupdate.php)
* [CSearchCustomRank::NextUpdate](/api_help/search/classes/csearchcustomrank/nextupdate.php)

Новинки документации в соцсетях: