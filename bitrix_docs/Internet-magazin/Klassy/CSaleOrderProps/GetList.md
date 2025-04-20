[Интернет-магазин](/api_help/sale/index.php)

[Классы](/api_help/sale/classes/index.php)

[CSaleOrderProps](/api_help/sale/classes/csaleorderprops/index.php)

GetList (доступен с 3.3.0)

GetList
=======

Включить вкладки

Описание и параметры

Возвращаемые значения

Пример использования

Метод устарел. Используйте методы класса [OrderBase](https://dev.1c-bitrix.ru/api_d7/bitrix/sale/classes/orderbase/index.php).

### Описание и параметры

```
CDBResult
CSaleOrderProps::GetList(
	array arOrder = array(),
	array arFilter = array(),
	array arGroupBy = false,
	array arNavStartParams = false,
	array arSelectFields = array()
);Копировать
```

Метод возвращает результат выборки из свойств заказов в соответствии со своими параметрами. Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| arOrder | Массив, в соответствии с которым сортируются результирующие записи. Массив имеет вид:  ``` array( 	"название_поля1" => "направление_сортировки1", 	"название_поля2" => "направление_сортировки2", 	. . . )Копировать ```  В качестве "название\_поля*N*" может стоять любое поле местоположения, а в качестве "направление\_сортировки*X*" могут быть значения "*ASC*" (по возрастанию) и "*DESC*" (по убыванию).    Если массив сортировки имеет несколько элементов, то результирующий набор сортируется последовательно по каждому элементу (т.е. сначала сортируется по первому элементу, потом результат сортируется по второму и т.д.).     Значение по умолчанию - пустой массив array() - означает, что результат отсортирован не будет. |
| arFilter | Массив, в соответствии с которым фильтруются записи свойств заказа. Массив имеет вид:  ``` array( 	"[модификатор1][оператор1]название_поля1" => "значение1", 	"[модификатор2][оператор2]название_поля2" => "значение2", 	. . . )Копировать ```  Удовлетворяющие фильтру записи возвращаются в результате, а записи, которые не удовлетворяют условиям фильтра, отбрасываются.    Допустимыми являются следующие модификаторы:  * **!** - отрицание; * **+** - значения null, 0 и пустая строка так же удовлетворяют условиям фильтра.  Допустимыми являются следующие операторы:  * **>=** - значение поля больше или равно передаваемой в фильтр величины; * **>** - значение поля строго больше передаваемой в фильтр величины; * **<=** - значение поля меньше или равно передаваемой в фильтр величины; * **<** - значение поля строго меньше передаваемой в фильтр величины; * **@** - значение поля находится в передаваемом в фильтр разделенном запятой списке значений. Можно передавать и фильтр. Для ключа **CODE** - корректно формирует фильтр только для массива, а не для перечисление через запятые.; * **~** - значение поля проверяется на соответствие передаваемому в фильтр шаблону; * **%** - значение поля проверяется на соответствие передаваемой в фильтр строке в соответствии с языком запросов.  В качестве "название\_поля" может стоять любое поле заказов.    Пример фильтра:  ``` array( 	"REQUIED" => "Y" )Копировать ```  Этот фильтр означает "выбрать все записи, в которых значение в поле REQUIED (обязательно для заполнения) равно Y".    Значение по умолчанию - пустой массив array() - означает, что результат отфильтрован не будет. |
| arGroupBy | Массив полей, по которым группируются записи свойств заказа. Массив имеет вид:  ``` array( 	"название_поля1", 	"группирующая_функция2" => "название_поля2",  	. . . )Копировать ```  В качестве "название\_поля*N*" может стоять любое поле свойств заказа. В качестве группирующей функции могут стоять:  * **COUNT** - подсчет количества; * **AVG** - вычисление среднего значения; * **MIN** - вычисление минимального значения; * **MAX** - вычисление максимального значения; * **UTIL** - флаг Y/N, служебное; * **SUM** - вычисление суммы.  Если массив пустой, то метод вернет число записей, удовлетворяющих фильтру.    Значение по умолчанию - *false* - означает, что результат группироваться не будет. |
| arNavStartParams | Массив параметров выборки. Может содержать следующие ключи:  * "**nTopCount**" - количество возвращаемых методом записей будет ограничено сверху значением этого ключа; * любой ключ, принимаемый методом  **CDBResult::NavQuery**   в качестве третьего параметра.  Значение по умолчанию - *false* - означает, что параметров выборки нет. |
| arSelectFields | Массив полей записей, которые будут возвращены методом. Можно указать только те поля, которые необходимы. Если в массиве присутствует значение "\*", то будут возвращены все доступные поля.    Значение по умолчанию - пустой массив array() - означает, что будут возвращены все поля основной таблицы запроса. |

### Возвращаемые значения

Возвращается объект класса CDBResult, содержащий набор ассоциативных массивов параметров свойств с ключами:

| Ключ | Описание |
| --- | --- |
| ID | Код свойства заказа. |
| PERSON\_TYPE\_ID | Тип плательщика. |
| NAME | Название свойства. |
| TYPE | Тип свойства. Допустимые значения:  * CHECKBOX - флаг, * TEXT - строка текста, * SELECT - выпадающий список значений, * MULTISELECT - список со множественным выбором, * TEXTAREA - многострочный текст, * LOCATION - местоположение, * RADIO - переключатель. |
| REQUIED | Флаг (Y/N) обязательное ли поле. |
| DEFAULT\_VALUE | Значение по умолчанию. |
| SORT | Индекс сортировки. |
| USER\_PROPS | Флаг (Y/N) входит ли это свойство в профиль покупателя. |
| IS\_LOCATION | Флаг (Y/N) использовать ли значение свойства как местоположение покупателя для расчёта стоимости доставки (только для свойств типа LOCATION) |
| PROPS\_GROUP\_ID | Код группы свойств. |
| SIZE1 | Ширина поля (размер по горизонтали). |
| SIZE2 | Высота поля (размер по вертикали). |
| DESCRIPTION | Описание свойства. |
| IS\_EMAIL | Флаг (Y/N) использовать ли значение свойства как E-Mail покупателя. |
| IS\_PROFILE\_NAME | Флаг (Y/N) использовать ли значение свойства как название профиля покупателя. |
| IS\_PAYER | Флаг (Y/N) использовать ли значение свойства как имя плательщика. |
| IS\_LOCATION4TAX | Флаг (Y/N) использовать ли значение свойства как местоположение покупателя для расчёта налогов (только для свойств типа LOCATION) |
| CODE | Символьный код свойства. |

Если в качестве параметра arGroupBy передается пустой массив, то метод вернет число записей, удовлетворяющих фильтру.

### Пример использования

```
<?
// Выведем форму для ввода свойств заказа для группы свойств с кодом 5, которые входят в профиль покупателя, для типа плательщика с кодом 2
$db_props = CSaleOrderProps::GetList(
	array("SORT" => "ASC"),
	array(
		"PERSON_TYPE_ID" => 2,
		"PROPS_GROUP_ID" => 5,
		"USER_PROPS" => "Y"
	),
	false,
	false,
	array()
);
if ($props = $db_props->Fetch())
{
	echo "Заполните параметры заказа:<br>";
	do
	{
		echo $props["NAME"];
		if ($props["REQUIED"]=="Y" || 
			$props["IS_EMAIL"]=="Y" || 
			$props["IS_PROFILE_NAME"]=="Y" || 
			$props["IS_LOCATION"]=="Y" || 
			$props["IS_LOCATION4TAX"]=="Y" || 
			$props["IS_PAYER"]=="Y"
		)
		{
		echo "*";
		}
		echo ": ";
		if ($props["TYPE"]=="CHECKBOX")
		{
			echo '<input type="checkbox" class="inputcheckbox" name="ORDER_PROP_'.$props["ID"].'" value="Y"'.(($props["DEFAULT_VALUE"]=="Y")?" checked":"").'>';
		}
		elseif ($props["TYPE"]=="TEXT")
		{
			echo '<input type="text" class="inputtext" size="'.((IntVal($props["SIZE1"])>0)?$props["SIZE1"]:30).'" maxlength="250" value="'.htmlspecialchars($props["DEFAULT_VALUE"]).'" name="ORDER_PROP_'.$props["ID"].'">';
		}
		elseif ($props["TYPE"]=="SELECT")
		{
			echo '<select name="ORDER_PROP_'.$props["ID"].'" size="'.((IntVal($props["SIZE1"])>0)?$props["SIZE1"]:1).'">';
			$db_vars = CSaleOrderPropsVariant::GetList(($by="SORT"), ($order="ASC"), Array("ORDER_PROPS_ID"=>$props["ID"]));
			while ($vars = $db_vars->Fetch())
			{
				echo '<option value="'.$vars["VALUE"].'"'.(($vars["VALUE"]==$props["DEFAULT_VALUE"])?" selected":"").'>'.htmlspecialchars($vars["NAME"]).'</option>';
			}
			echo '</select>';
		}
		elseif ($props["TYPE"]=="MULTISELECT")
		{
			echo '<select multiple name="ORDER_PROP_'.$props["ID"].'[]" size="'.((IntVal($props["SIZE1"])>0)?$props["SIZE1"]:5).'">';
			$arDefVal = Split(",", $props["DEFAULT_VALUE"]);
			for ($i = 0; $i<count($arDefVal); $i++)
				$arDefVal[$i] = Trim($arDefVal[$i]);
			$db_vars = CSaleOrderPropsVariant::GetList(($by="SORT"), ($order="ASC"), Array("ORDER_PROPS_ID"=>$props["ID"]));
			while ($vars = $db_vars->Fetch())
			{
				echo '<option value="'.$vars["VALUE"].'"'.(in_array($vars["VALUE"], $arDefVal)?" selected":"").'>'.htmlspecialchars($vars["NAME"]).'</option>';
			}
			echo '</select>';
		}
		elseif ($props["TYPE"]=="TEXTAREA")
		{
			echo '<textarea rows="'.((IntVal($props["SIZE2"])>0)?$props["SIZE2"]:4).'" cols="'.((IntVal($props["SIZE1"])>0)?$props["SIZE1"]:40).'" name="ORDER_PROP_'.$props["ID"].'">'.htmlspecialchars($props["DEFAULT_VALUE"]).'</textarea>';
		}
		elseif ($props["TYPE"]=="LOCATION")
		{
			echo '<select name="ORDER_PROP_'.$props["ID"].'" size="'.((IntVal($props["SIZE1"])>0)?$props["SIZE1"]:1).'">';
			$db_vars = CSaleLocation::GetList(Array("SORT"=>"ASC", "COUNTRY_NAME_LANG"=>"ASC", "CITY_NAME_LANG"=>"ASC"), array(), LANGUAGE_ID);
			while ($vars = $db_vars->Fetch())
			{
				echo '<option value="'.$vars["ID"].'"'.((IntVal($vars["ID"])==IntVal($props["DEFAULT_VALUE"]))?" selected":"").'>'.htmlspecialchars($vars["COUNTRY_NAME"]." - ".$vars["CITY_NAME"]).'</option>';
			}
			echo '</select>';
		}
		elseif ($props["TYPE"]=="RADIO")
		{
			$db_vars = CSaleOrderPropsVariant::GetList(($by="SORT"), ($order="ASC"), Array("ORDER_PROPS_ID"=>$props["ID"]));
			while ($vars = $db_vars->Fetch())
			{
				echo '<input type="radio" name="ORDER_PROP_'.$props["ID"].'" value="'.$vars["VALUE"].'"'.(($vars["VALUE"]==$props["DEFAULT_VALUE"])?" checked":"").'>'.htmlspecialchars($vars["NAME"]).'<br>';
			}
		}
		if (strlen($props["DESCRIPTION"])>0)
		{
			echo "<br><small>".$props["DESCRIPTION"]."</small>";
		}
		echo "<br>";
	}
	while ($props = $db_props->Fetch());
}
?>Копировать
```

Новинки документации в соцсетях: