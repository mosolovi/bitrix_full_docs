[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockType](/api_help/iblock/classes/ciblocktype/index.php)

Add (доступен с 3.1.3)

Add
===

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
bool
CIBlockType::Add(
	array arFields
);Копировать
```

Метод добавляет новый тип информационных блоков. Нестатический метод.

**Примечание:** вызов метода без ключа **LANG** или с пустым ключом вызывает ошибку.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arFields | Массив поле=>значение... Содержит значения [полей типа информационных блоков](/api_help/iblock/fields.php#fiblocktype). В элементе массива arFields["LANG"] должен содержаться ассоциативный массив [языковых свойств](/api_help/iblock/fields.php#fiblocktypelang) типа.Ключами этого массива служат идентификаторы языков. |

#### Возвращаемое значение

Метод возвращает:

* `true` — если тип успешно добавлен
* `false` — при возникновении ошибки

В случае ошибки в свойстве объекта `LAST_ERROR` будет содержаться текст ошибки. Получить текст ошибки можно методом [getLastError](/api_help/iblock/classes/ciblocktype/getlasterror.php).

### Смотрите также

* [CIBlockType](/api_help/iblock/classes/ciblocktype/index.php)::[Update()](/api_help/iblock/classes/ciblocktype/update.php)
* [Поля типа информационных блоков](/api_help/iblock/fields.php#fiblocktype)

### Примеры использования

```
<?
$arFields = Array(
	'ID'=>'catalog',
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
$res = $obBlocktype->Add($arFields);
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