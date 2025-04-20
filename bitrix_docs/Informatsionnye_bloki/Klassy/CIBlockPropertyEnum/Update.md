[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockPropertyEnum](/api_help/iblock/classes/ciblockpropertyenum/index.php)

Update (доступен с 3.1.3)

Update
======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
bool CIBlockPropertyEnum::Update(
	int ID,
	array arFields
);Копировать
```

Метод изменяет параметры варианта свойства с кодом *ID*. Метод статический.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | ID изменяемой записи. |
| arFields | Массив Array("поле"=>"значение", ...). Содержит значения [всех полей](/api_help/iblock/fields.php#fpropertyenum) варианта значения свойства. |

#### Возвращаемое значение

Метод возвращает true если изменение прошло успешно, при возникновении ошибки метод вернет false.

### Смотрите также

* [CIBlockPropertyEnum::Add](/api_help/iblock/classes/ciblockpropertyenum/add.php)
* [Поля свойства](/api_help/iblock/fields.php#fpropertyenum)

### Примеры использования

#### Примеры использования

```
<?
$ibpenum = new CIBlockPropertyEnum;
$ibpenum->Update($PROPERTY_ENUM_ID, Array('VALUE'=>'Enum 1'));
?>Копировать
```

Новинки документации в соцсетях: