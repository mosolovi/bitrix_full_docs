[Интернет-магазин](/api_help/sale/index.php)

[Классы](/api_help/sale/classes/index.php)

[CSaleTaxRate](/api_help/sale/classes/csaletaxrate/index.php)

GetList (доступен с 3.3.1)

GetList
=======

Включить вкладки

Описание и параметры

Возвращаемые значения

Пример использования

### Описание и параметры

```
CDBResult
CSaleTaxRate::GetList(
	array arOrder = array("APPLY_ORDER"=>"ASC"),
	array arFilter = array()
);Копировать
```

Метод возвращает набор ставок налога, удовлетворяющих фильтру arFilter. Набор упорядочен в соответствии с массивом arOrder. Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| arOrder | Ассоциативный массив для сортировки результирующего набора ставок налогов. Набор сортируется последовательно по каждой паре ключ-значение массива. Ключами массива являются названия параметров ставки налога, по значениям которых осуществляется сортировка. Значениями являются направления сортировки.   Допустимые ключи:  * **APPLY\_ORDER** - порядок применения; * **ID** - код ставки налога; * **LID** - сайт налога; * **CODE** - символьный код налога; * **TIMESTAMP\_X** - дата последнего изменения параметров ставки; * **ACTIVE** - флаг (Y/N) активности ставки; * **NAME** - название налога; * **PERSON\_TYPE\_ID** - тип плательщика ставки; * **IS\_IN\_PRICE** - флаг (Y/N) входит ли ставка налога в цену  Допустимые значения:  * ASC - по возрастанию; * DESC - по убыванию. |
| arFilter | Ассоциативный массив условий для отбора (фильтрации) ставок налогов. Ключами являются названия фильтруемых параметров ставки налога, а значениями - условия на значения.   Допустимые ключи:  * **ID** - код ставки налога; * **LID** - сайт налога; * **CODE** - символьный код налога; * **TAX\_ID** - код налога; * **PERSON\_TYPE\_ID** - тип плательщика ставки налога; * **IS\_IN\_PRICE** - флаг (Y/N) входит ли налог в цену; * **ACTIVE** - флаг (Y/N) активности ставки налога; * **APPLY\_ORDER** - порядок применения; * **LOCATION** - код местоположения, в котором действует ставка. |

### Возвращаемые значения

Возвращается объект класса CDBResult, содержащий ассоциативные массивы параметров ставок налогов с ключами:

| Ключ | Описание |
| --- | --- |
| ID | Код ставки налога. |
| TAX\_ID | Код налога. |
| PERSON\_TYPE\_ID | Тип плательщика. |
| VALUE | Величина налога (в процентах) |
| CURRENCY | Валюта. |
| IS\_PERCENT | Y |
| IS\_IN\_PRICE | Флаг (Y/N) входит ли уже налог в цену. |
| APPLY\_ORDER | Порядок применения. |
| TIMESTAMP\_X | Дата последнего изменения записи. |
| LID | Сайт налога. |
| NAME | Название налога. |
| CODE | Символьный код налога. |
| DESCRIPTION | Описание налога. |
| ACTIVE | Флаг (Y/N) активности ставки. |

### Пример использования

```
<?
// Заполним массив активных ставок налогов на текущем сайте для типа плательщика 
// с кодом $PERSON_TYPE и местоположением плательщика с кодом $TAX_LOCATION
$arTaxList = array();
$arTaxFilter = array(
	"LID" => SITE_ID,
	"PERSON_TYPE_ID" => $PERSON_TYPE,
	"ACTIVE" => "Y",
	"LOCATION" => $TAX_LOCATION
);
$db_tax_rate_tmp = CSaleTaxRate::GetList(array("APPLY_ORDER"=>"ASC"), $arTaxFilter);
while ($ar_tax_rate_tmp = $db_tax_rate_tmp->Fetch())
{
	$arTaxList[] = $ar_tax_rate_tmp;
}
?>Копировать
```

Новинки документации в соцсетях: