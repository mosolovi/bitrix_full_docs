[Информационные блоки](/api_help/iblock/index.php)

[События](/api_help/iblock/events/index.php)

OnIBlockElementSetPropertyValues (доступно с 15.5.12)

OnIBlockElementSetPropertyValues
================================

Включить вкладки

Описание и параметры

Смотрите также

### Описание и параметры

```
функция-обработчик(
	int ELEMENT_ID,
	int IBLOCK_ID,
	array PROPERTY_VALUES,
	string PROPERTY_CODE,
	array ar_prop,
	array arDBProps    
);Копировать
```

Событие *OnIBlockElementSetPropertyValues* вызывается в момент сохранения значений свойств элемента инфоблока.

Событие вызывается в момент, когда уже отработали все обработчики, изменяющие данные, а также уже произошла проверка данных и идет запись в базу. Изменять данные событие не позволяет. Основной сценарий использования - выполнить некий код перед работой с базой, будучи уверенным, что данные в базе будут изменены.

#### Параметры

| Параметр | Описание |
| --- | --- |
| ELEMENT\_ID | Идентификатор элемента инфоблока. |
| IBLOCK\_ID | Идентификатор инфоблока. |
| PROPERTY\_VALUES | [Массив значений свойств](/api_help/iblock/classes/ciblockelement/setpropertyvalues.php) элемента инфоблока. |
| PROPERTY\_CODE | Код изменяемого свойства. Если этот параметр отличен от *false*, то изменяется только свойство с таким кодом. |
| ar\_prop | Массив, описывающий активные свойства инфоблока. |
| arDBProps | Текущие значения свойств элемента. |

#### Возвращаемое значение

Нет.

### Смотрите также

* [CIBlockElement::SetPropertyValues](/api_help/iblock/classes/ciblockelement/setpropertyvalues.php)

Новинки документации в соцсетях: