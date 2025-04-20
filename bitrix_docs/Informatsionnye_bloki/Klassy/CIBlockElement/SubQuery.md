[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockElement](/api_help/iblock/classes/ciblockelement/index.php)

SubQuery (доступен с 10.0.2)

SubQuery
========

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
object
CIBlockElement::SubQuery(
	string strField,
	array arFilter
);Копировать
```

Позволяет использовать подзапросы. Метод статический.

**Примечание**: применимо только к полю **ID** элемента основного запроса.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| strField | Название поля, по которому будет осуществляться фильтрация.   Возможные значения:    * **ID** - по идентификатору элемента  * **PROPERTY\_<PROPERTY\_CODE>** - по значению свойства, где **PROPERTY\_CODE** - это ID или символьный код свойства привязки. Свойство должно быть типа "привязка к элементам". |
| arFilter | Фильтр элементов тот же, что и в методе [CIBlockElement::GetList](/api_help/iblock/classes/ciblockelement/getlist.php) за исключением того, что с версии 23.0.0 принимается ключ `IBLOCK_ID` либо `=IBLOCK_ID`. Значение - одиночное (ID одного инфоблока) |

#### Возвращаемое значение

Объект подзапроса.

### Примеры использования

```
<?
//Выбрать авторов написавших книги в 21-ом веке.
if(CModule::IncludeModule('iblock'))
{
	$rsBooks = CIBlockElement::GetList(
		array("NAME" => "ASC"), //Сортируем по имени
		array(
			"IBLOCK_ID" => $AUTHOR_IBLOCK,
			"ACTIVE" => "Y",
			"ID" => CIBlockElement::SubQuery("PROPERTY_AUTHOR", array(
				"IBLOCK_ID" => $BOOK_IBLOCK,
				">=PROPERTY_PRINT_DATE" => "2000-01-01 00:00:00",
			)),
		),
		false, // Без группировки
		false,  //Без постранички
		array("ID", "IBLOCK_ID", "NAME") // Выбираем только поля необходимые для показа
	);
	while($arBook = $rsBooks->GetNext())
		echo "<li>", $arBook["NAME"],"\n";
}
?>Копировать
```

  

#### Смотрите также

* [CIBlockElement::GetList](/api_help/iblock/classes/ciblockelement/getlist.php)

Новинки документации в соцсетях: