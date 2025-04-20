[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockPropertyEnum](/api_help/iblock/classes/ciblockpropertyenum/index.php)

Add (доступен с 3.1.3)

Add
===

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
int CIBlockPropertyEnum::Add(
	array fields
);Копировать
```

Метод добавляет новый вариант значения свойства типа "список". Метод статический.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| fields | Массив Array("поле"=>"значение", ...). Содержит значения [всех полей](/api_help/iblock/fields.php#fpropertyenum) варианта значения свойства. |

#### Возвращаемое значение

Метод возвращает код добавленного свойства, если добавление прошло успешно, при возникновении ошибки метод вернет false.

### Смотрите также

* [CIBlockPropertyEnum::Update](/api_help/iblock/classes/ciblockpropertyenum/update.php)
* [Поля вариантов значения свойств типа "список"](/api_help/iblock/fields.php#fpropertyenum)

### Примеры использования

```
<?
$ibpenum = new CIBlockPropertyEnum;
if($PropID = $ibpenum->Add(Array('PROPERTY_ID'=>$PROPERTY_ID, 'VALUE'=>'New Enum 1')))
	echo 'New ID:'.$PropID;
?>Копировать
```

Новинки документации в соцсетях: