[Информационные блоки](/api_help/iblock/index.php)

[События](/api_help/iblock/events/index.php)

OnIBlockElementSetPropertyValuesEx (с версии 17.6.5)

OnIBlockElementSetPropertyValuesEx
==================================

Включить вкладки

Описание и параметры

Смотрите также

### Описание и параметры

```
функция-обработчик(
	int ELEMENT_ID,
	int IBLOCK_ID,
	array PROPERTY_VALUES,
	array propertyList,
	array arDBProps    
);Копировать
```

Событие вызывается до внесения изменений в базу после валидации входящих данных.

#### Параметры

| Параметр | Описание |
| --- | --- |
| ELEMENT\_ID | Идентификатор элемента инфоблока. |
| IBLOCK\_ID | Идентификатор инфоблока. |
| PROPERTY\_VALUES | [Массив значений свойств](/api_help/iblock/classes/ciblockelement/setpropertyvalues.php) элемента инфоблока. |
| propertyList | Массив, описывающий Список свойств. |
| arDBProps | Текущие значения свойств элемента. |

#### Возвращаемое значение

Нет.

### Смотрите также

* [CIBlockElement::SetPropertyValuesEx](/api_help/iblock/classes/ciblockelement/setpropertyvaluesex.php)

Новинки документации в соцсетях: