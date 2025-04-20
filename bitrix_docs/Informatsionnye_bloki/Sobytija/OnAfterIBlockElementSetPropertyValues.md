[Информационные блоки](/api_help/iblock/index.php)

[События](/api_help/iblock/events/index.php)

OnAfterIBlockElementSetPropertyValues (доступно с 14.5.1)

OnAfterIBlockElementSetPropertyValues
=====================================

Включить вкладки

Описание и параметры

Смотрите также

### Описание и параметры

```
функция-обработчик(
	int ELEMENT_ID,
	int IBLOCK_ID,
	array PROPERTY_VALUES,
	string PROPERTY_CODE
);Копировать
```

Событие "OnAfterIBlockElementSetPropertyValues" вызывается после попытки сохранения значений всех свойств элемента инфоблока методом [CIBlockElement::SetPropertyValues](/api_help/iblock/classes/ciblockelement/setpropertyvalues.php).

#### Параметры

| Параметр | Описание |
| --- | --- |
| ELEMENT\_ID | Код элемента, значения свойств которого необходимо установить. |
| IBLOCK\_ID | Код информационного блока. |
| PROPERTY\_VALUES | Массив значений свойств, в котором коду свойства ставится в соответствие значение свойства. |
| PROPERTY\_CODE | Код изменяемого свойства. |

#### Возвращаемое значение

Нет.

### Смотрите также

* [CIBlockElement::SetPropertyValues](/api_help/iblock/classes/ciblockelement/setpropertyvalues.php)

Новинки документации в соцсетях: