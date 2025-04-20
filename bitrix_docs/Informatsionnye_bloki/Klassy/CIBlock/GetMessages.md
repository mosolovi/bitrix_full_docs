[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlock](/api_help/iblock/classes/ciblock/index.php)

GetMessages (доступен с 7.0.0)

GetMessages
===========

```
array
CIBlock::GetMessages(
	int ID,
	string type=""
);Копировать
```

Метод возвращает значения [дополнительных полей](/api_help/iblock/fields.php#fiblocklang) инфоблока. Метод статический.

#### Параметры вызова

| Параметр | Описание | С версии |
| --- | --- | --- |
| ID | Код инфоблока. |  |
| type | Код типа инфоблоков.    Параметр используется только тогда, когда инфоблок с указанным ID не найден или указан 0. В этом случае берутся значения дополнительных полей из этого типа.   Если ID задан и такой инфоблок есть, то параметр type игнорируется. | 8.6.3 |

#### Возвращаемое значение

Массив значений [дополнительных полей](/api_help/iblock/fields.php#fiblocklang) инфоблока.

#### Смотрите также

* [CIBlock::SetMessages](/api_help/iblock/classes/ciblock/SetMessages.php)
* [Дополнительные поля](/api_help/iblock/fields.php#fiblocklang)

Новинки документации в соцсетях: