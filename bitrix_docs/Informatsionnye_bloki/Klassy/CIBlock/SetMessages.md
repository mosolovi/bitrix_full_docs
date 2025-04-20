[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlock](/api_help/iblock/classes/ciblock/index.php)

SetMessages (доступен с 7.0.0)

SetMessages
===========

```
CIBlock::SetMessages(
	int ID,
	array arFields
);Копировать
```

Метод устанавливает значения [дополнительных полей](/api_help/iblock/fields.php#fiblocklang) инфоблока. Вызывается в методах [CIBlock::Add](/api_help/iblock/classes/ciblock/add.php) и [CIBlock::Update](/api_help/iblock/classes/ciblock/update.php). Нестатический метод.

**Примечание**: значения полей не указанных в параметре arFields сохраняются.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | Код инфоблока |
| arFields | Массив вида array("Поле" => "Значение" ...) |

#### Возвращаемое значение

Метод ничего не возвращает.

#### Смотрите также

* [Дополнительные поля](/api_help/iblock/fields.php#fiblocklang)

Новинки документации в соцсетях: