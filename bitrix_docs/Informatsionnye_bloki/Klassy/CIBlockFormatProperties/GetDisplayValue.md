[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockFormatProperties](/api_help/iblock/classes/ciblockformatproperties/index.php)

GetDisplayValue (доступен с 5.9.0)

GetDisplayValue
===============

```
array CIBlockFormatProperties::GetDisplayValue(
	array arItem, 
	array arProperty, 
) Копировать
```

Метод помогает компонентам показать значения свойства элемента. Вынесен в модуль для унификации отображения. Метод статический.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| arItem | Массив полей элемента. |
| arProperty | Массив полей свойства (как его возвращает метод [CIBlockElement::GetProperty](/api_help/iblock/classes/ciblockelement/getproperty.php)). |

#### Возвращаемое значение

Массив полей элемента.

**Примечание:** метод в поле DISPLAY\_VALUE выводит только активные по дате элементы (используется фильтр на уровне ядра, поэтому вывести ссылки на неактивные элементы не получится стандартными средствами).

Новинки документации в соцсетях: