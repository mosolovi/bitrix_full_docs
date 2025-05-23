[Интернет-магазин](/api_help/sale/index.php)

[Классы](/api_help/sale/classes/index.php)

[CSaleOrderProps](/api_help/sale/classes/csaleorderprops/index.php)

Update (доступен с 3.3.0)

Update
======

Включить вкладки

Описание и параметры

Пример использования

Метод устарел. Используйте методы класса [OrderBase](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/orderbase/index.php).

### Описание и параметры

```
int
CSaleOrderProps::Update( 
	int ID,
	array arFields
);Копировать
```

Метод изменяет параметры свойства с кодом ID заказа на значения из массива arFields. Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | Код свойства заказа. |
| arFields | Ассоциативный массив новых значений параметров свойства заказа, в котором ключами являются названия параметров свойства, а значениями - значения этих параметров.  Допустимые ключи:  * **PERSON\_TYPE\_ID** - тип плательщика; * **NAME** - название свойства (тип плательщика зависит от сайта, а сайт - от языка; название должно быть на соответствующем языке); * **TYPE** - тип свойства. Допустимые значения:   + **CHECKBOX** - флаг;   + **TEXT** - строка текста;   + **SELECT** - выпадающий список значений;   + **MULTISELECT** - список со множественным выбором;   + **TEXTAREA** - многострочный текст;   + **LOCATION** - местоположение;   + **RADIO** - переключатель. * **REQUIED** - (Y/N) флаг обязательности; * **DEFAULT\_VALUE** - значение по умолчанию; * **SORT** - индекс сортировки; * **USER\_PROPS** - флаг (Y/N) входит ли это свойство в профиль покупателя; * **IS\_LOCATION** - флаг (Y/N) использовать ли значение свойства как местоположение покупателя для расчёта стоимости доставки (только для свойств типа LOCATION); * **PROPS\_GROUP\_ID** - код группы свойств; * **SIZE1** - ширина поля (размер по горизонтали); * **SIZE2** - высота поля (размер по вертикали); * **DESCRIPTION** - описание свойства; * **IS\_EMAIL** - флаг (Y/N) использовать ли значение свойства как E-Mail покупателя; * **IS\_PROFILE\_NAME** - флаг (Y/N) использовать ли значение свойства как название профиля покупателя; * **IS\_PAYER** - флаг (Y/N) использовать ли значение свойства как имя плательщика; * **IS\_LOCATION4TAX** - флаг (Y/N) использовать ли значение свойства как местоположение покупателя для расчёта налогов (только для свойств типа **LOCATION**); * **CODE** - символьный код свойства. |

#### Возвращаемые значения

Возвращается числовой id свойства в случае успеха или bool false в случае ошибки, а ошибку следует добывать из `$APPLICATION: $APPLICATION->GetException()->GetString()`

### Пример использования

```
<?
$arFields = array(
	"PERSON_TYPE_ID" => 2,
	"NAME" => "Комплектация",
	"TYPE" => "RADIO",
	"REQUIED" => "Y",
	"DEFAULT_VALUE" => "F",
	"SORT" => 100,
	"CODE" => "COMPLECT",
	"USER_PROPS" => "N",
	"IS_LOCATION" => "N",
	"IS_LOCATION4TAX" => "N",
	"PROPS_GROUP_ID" => 1,
	"SIZE1" => 0,
	"SIZE2" => 0,
	"DESCRIPTION" => "",
	"IS_EMAIL" => "N",
	"IS_PROFILE_NAME" => "N",
	"IS_PAYER" => "N"
);
 
// Если установлен код свойства, то изменяем свойство с этим кодом,
// иначе добавляем новой свойство
if ($ID>0)
{
	if (!CSaleOrderProps::Update($ID, $arFields))
	{
		echo "Ошибка изменения параметров свойства";
	}
	else
	{
		// Обновим символьный код у значений свойства
		// (хранение избыточных данных для оптимизации работы)
		$db_order_props_tmp = 
			CSaleOrderPropsValue::GetList(($b="NAME"), 
				($o="ASC"),
				Array("ORDER_PROPS_ID"=>$ID));
		while ($ar_order_props_tmp = $db_order_props_tmp->Fetch())
		{
			CSaleOrderPropsValue::Update($ar_order_props_tmp["ID"],
				array("CODE" => "COMPLECT"));
		}
	}
}
else
{
	$ID = CSaleOrderProps::Add($arFields);
	if ($ID<=0)
		echo "Ошибка добавления свойства";
}
?>Копировать
```

Новинки документации в соцсетях: