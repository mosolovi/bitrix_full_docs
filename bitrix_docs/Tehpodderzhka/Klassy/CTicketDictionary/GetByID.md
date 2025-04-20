[Техподдержка](/api_help/support/index.php)

[Классы](/api_help/support/classes/index.php)

[CTicketDictionary](/api_help/support/classes/cticketdictionary/index.php)

GetByID (3.0.1)

GetByID
=======

```
record set
CTicketDictionary::GetByID(
	int ID
);Копировать
```

Метод возвращает данные по одной записи справочника. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| **ID** | ID записи. |

#### Пример массива одной строки выборки возвращаемой методом CTicketDictionary::GetByID

```
Array
(
	[ID] => 3
	[LID] => ru
	[C_TYPE] => C
	[SID] => 
	[SET_AS_DEFAULT] => N
	[C_SORT] => 500
	[NAME] => Доставка программного продукта и обновлений
	[DESCR] => 
	[RESPONSIBLE_USER_ID] => 2
	[EVENT1] => ticket
	[EVENT2] => 
	[EVENT3] => 
)Копировать
```

Новинки документации в соцсетях: