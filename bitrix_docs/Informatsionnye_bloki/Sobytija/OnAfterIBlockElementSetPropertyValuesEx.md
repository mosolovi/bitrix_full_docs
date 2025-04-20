[Информационные блоки](/api_help/iblock/index.php)

[События](/api_help/iblock/events/index.php)

OnAfterIBlockElementSetPropertyValuesEx (доступно с 14.5.1)

OnAfterIBlockElementSetPropertyValuesEx
=======================================

Включить вкладки

Описание и параметры

Смотрите также

### Описание и параметры

```
функция-обработчик(
	int ELEMENT_ID,
	int IBLOCK_ID,
	array PROPERTY_VALUES,
	array FLAGS
);Копировать
```

Событие "OnAfterIBlockElementSetPropertyValuesEx" вызывается после попытки сохранения значений свойств элемента инфоблока методом [CIBlockElement::SetPropertyValuesEx](/api_help/iblock/classes/ciblockelement/setpropertyvaluesex.php).

#### Параметры

| Параметр | Описание |
| --- | --- |
| ELEMENT\_ID | Код элемента, значения свойств которого необходимо установить. |
| IBLOCK\_ID | Код информационного блока. |
| PROPERTY\_VALUES | Массив значений свойств, в котором коду свойства ставится в соответствие значение свойства. |
| FLAGS | Массив параметров для оптимизации запросов к БД. Может содержать следующие ключи:  * NewElement - можно указать если заведомо известно, что значений свойств у данного элемента нет. Экономит один запрос к БД. * DoNotValidateLists - для свойств типа "список" отключает проверку наличия значений в метаданных свойства. |

#### Возвращаемое значение

Нет.

### Смотрите также

* [CIBlockElement::SetPropertyValuesEx](/api_help/iblock/classes/ciblockelement/setpropertyvaluesex.php)

Новинки документации в соцсетях: