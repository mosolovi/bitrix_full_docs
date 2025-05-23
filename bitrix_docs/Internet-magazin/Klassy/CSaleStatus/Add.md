[Интернет-магазин](/api_help/sale/index.php)

[Классы](/api_help/sale/classes/index.php)

[CSaleStatus](/api_help/sale/classes/csalestatus/index.php)

Add (доступен с 3.3.0)

Add
===

```
string
CSaleStatus::Add(
	array arFields
);Копировать
```

Метод добавляет новый статус заказа с параметрами из массива arFields. Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| arFields | Ассоциативный массив параметров нового статуса. Ключами в массиве являются названия параметров статуса, а значениями - соответствующие значения.  Допустимые ключи:  * **ID** - код статуса (обязательный), состоит из одной буквы; * **SORT** - индекс сортировки; * **LANG** - массив ассоциативных массивов языкозависимых параметров статуса с ключами:   + **LID** - язык;   + **NAME** - название статуса на этом языке;   + **DESCRIPTION** - описание статуса; * **PERMS** - массив ассоциативных массивов прав на доступ к изменению заказа в данном статусе с ключами:   + **GROUP\_ID** - группа пользователей;   + **PERM\_TYPE** - тип доступа (S - разрешен перевод заказа в данный статус, M - разрешено изменение заказа в данном статусе). |

#### Возвращаемые значения

Возвращается код добавленного статуса или *false* в случае ошибки.

Новинки документации в соцсетях: