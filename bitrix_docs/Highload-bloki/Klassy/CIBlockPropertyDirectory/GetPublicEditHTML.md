[Highload-блоки](/api_help/hlblock/index.php)

[Классы](/api_help/hlblock/classes/index.php)

[CIBlockPropertyDirectory](/api_help/hlblock/classes/ciblockpropertydirectory/index.php)

GetPublicEditHTML (доступен с 16.5.0)

GetPublicEditHTML
=================

```
string 
CIBlockPropertyDirectory::GetPublicEditHTML(
	array property,
	array value,
	array control
);Копировать
```

Метод должен вернуть HTML отображения элемента управления для редактирования значений свойства в публичной части сайта. Метод статический.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| property | Метаданные свойства. См. [Свойства элементов инфоблока](/api_help/iblock/fields.php#fproperty) . |
| value | Значение свойства. Массив вида:   array(   "VALUE" => значение,   "DESCRIPTION" => описание,   ); |
| control | Имена элементов управления для заполнения значения свойства и его описания. Массив вида:   array(   "VALUE" => html безопасное имя для значения,   "DESCRIPTION" => html безопасное имя для описания,   "FORM\_NAME" => имя формы в которую будет встроен элемент управления.   ); |

#### Возвращаемое значение

Строка.

Новинки документации в соцсетях: