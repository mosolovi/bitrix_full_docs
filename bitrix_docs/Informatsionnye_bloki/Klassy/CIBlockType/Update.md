[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockType](/api_help/iblock/classes/ciblocktype/index.php)

Update (доступен с 3.1.3)

Update
======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
bool
CIBlockType::Update(
	string ID,
	array arFields
);Копировать
```

Метод изменяет параметры типа информационных блоков с кодом *ID*. Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | Код изменяемой записи. |
| arFields | Массив поле=>значение... Содержит значения [полей типа информационных блоков](/api_help/iblock/fields.php#fiblocktype). В элементе массива arFields["LANG"] должен содержаться ассоциативный массив [языковых свойств](/api_help/iblock/fields.php#fiblocktypelang) типа. Ключами этого массива служат идентификаторы языков. |

#### Возвращаемое значение

Метод возвращает:

* `true` — если изменение прошло успешно
* `false` — при возникновении ошибки

В случае ошибки в свойстве объекта `LAST_ERROR` будет содержаться текст ошибки. Получить текст ошибки можно методом [getLastError](/api_help/iblock/classes/ciblocktype/getlasterror.php).

### Смотрите также

* [CIBlockType](/api_help/iblock/classes/ciblocktype/index.php)::[Add()](/api_help/iblock/classes/ciblocktype/add.php)
* [Поля типа информационных блоков](/api_help/iblock/fields.php#fiblocktype)

### Примеры использования

```
<?
$arFields = Array(
	'SECTIONS'=>'Y',
	'IN_RSS'=>'N',
	'SORT'=>100,
	'LANG'=>Array(
		'en'=>Array(
			'NAME'=>'Catalog',
			'SECTION_NAME'=>'Sections',
			'ELEMENT_NAME'=>'Products'
		)
	)
);
$obBlocktype = new CIBlockType;
$DB->StartTransaction();
$res = $obBlocktype->Update('catalog', $arFields);
if(!$res)
{
	$DB->Rollback();
	echo 'Error: '.$obBlocktype->LAST_ERROR.'<br>';
}
else
	$DB->Commit();
?>Копировать
```

Новинки документации в соцсетях: