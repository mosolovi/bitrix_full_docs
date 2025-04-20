[Информационные блоки](/api_help/iblock/index.php)

[Функции](/api_help/iblock/functions/index.php)

GetIBlockElementListEx (доступна с 3.0.5)

GetIBlockElementListEx
======================

Включить вкладки

Описание

Параметры функции

Смотрите также

Примеры использования

### Описание

```
CIBlockResult
GetIBlockElementListEx (
	string type, 
	mixed TypesInc = Array(), 
	mixed TypesExc = Array(), 
	array Order = Array("SORT"=>"ASC"), 
	int cnt = 0, 
	array arFilter = Array(), 
	array arSelect = Array(), 
	mixed arGroupBy = false
);Копировать
```

Функция возвращает активные для текущего сайта элементы из информационных
блоков типа *type*. Функция работает только с активными инфоблоками, так как в ней принудительно выставлен фильтр по активности инфоблока.

#### Возвращаемое значение

Функция возвращает объект класса [CIBlockResult](/api_help/iblock/classes/ciblockresult/index.php) с активными
элементами (у которых установлен флаг "Активен", выполняется условие периода
активности и находящиеся в активных информационных блоках для текущего
сайта).

**Примечание:** при работе с результатом рекомендуется применять метод класса [CDBResult](/api_help/main/reference/cdbresult/index.php)::[GetNext()](/api_help/main/reference/cdbresult/getnext.php),
результатом которого будет массив с полями элемента информационного блока. Все
поля при этом будут преобразованы в "HTML безопасный" вид, а в полях с шаблонами
URL-ов к страницам (*LIST\_PAGE\_URL* - списка элементов и
*DETAIL\_PAGE\_URL* - детального просмотра) будут заменены параметры
`#SITE_DIR#`, `#IBLOCK_ID#`, `#EXTERNAL_ID#` и
`#ID#`. Если результат пуст или достигнут конец выборки [CDBResult](/api_help/main/reference/cdbresult/index.php)::[GetNext()](/api_help/main/reference/cdbresult/getnext.php)
вернет false. Также можно воспользоваться любыми другими методами класса [CDBResult](/api_help/main/reference/cdbresult/index.php),
но при этом в полях *LIST\_PAGE\_URL* и *DETAIL\_PAGE\_URL* будут
оригинальные (как они введены в форме редактирования информационного блока)
шаблоны URL-ов, а не с замененными параметрами `#SITE_DIR#`,
`#IBLOCK_ID#`, `#EXTERNAL_ID#` и `#ID#`.

### Параметры функции

| Параметр | Описание |
| --- | --- |
| type | Тип информационных блоков из которых выбираются элементы. |
| TypesInc | Фильтр для включения по ID и(или) символьному коду информационного блока. В качестве параметра может быть как единичное значение (ID или символьный код информационного блока), так и массив (array) таких значений. Необязательный. По умолчанию включаются все элементы из информационных блоков типа type без дополнительной фильтрации. Пример: "product\_news" |
| TypesExc | Фильтр для исключения по ID и(или) символьному коду информационного блока. В качестве параметра может быть как единичное значение (ID или символьный код информационного блока), так и массив (array) таких значений. Необязательный. По умолчанию выбираются все элементы из информационных блоков типа type без исключений. Пример: Array("company\_news", "product\_news", 22) |
| Order | Порядок сортировки - массив вида Array(*by1*=>*order1*[, *by2*=>*order2* [, ..]]), где *by* - поле для сортировки, может принимать значения:  * **sort** - индекс сортировки; * **timestamp\_x** - дата изменения; * **name** - название; * **id** - ID элемента; * **active\_from** - начало периода действия элемента; * **active\_to** - окончание периода действия элемента; * **order** - порядок сортировки сортировки, может принимать   значения:   + **asc** - по возрастанию;   + **desc** - по убыванию.Необязательный. По умолчанию   равен *Array("sort"=>"asc")*  Полный список полей сортировки и дополнительную информацию [смотрите](/api_help/iblock/classes/ciblockelement/getlist.php) в [CIBlockElement](/api_help/iblock/classes/ciblockelement/index.php)::[GetList()](/api_help/iblock/classes/ciblockelement/getlist.php) |
| cnt | Максимальное количество записей, которые вернет функция.  Необязательный. По умолчанию выбираются все записи. |
| arFilter | Дополнительный фильтр по произвольным полям вида Array("Фильтруемое поле"=>"Значение", ...).  *Фильтруемое поле* может принимать значения:  * **ID** - по коду; * **ACTIVE** - фильтр по активности (Y|N); передача пустого   значения (*"ACTIVE"=>""*) выводит все элементы без учета их   состояния; * **NAME** - по имени и фамилии (можно искать по шаблону [%\_]); * **PREVIEW\_TEXT** - по имени и фамилии (можно искать по шаблону   [%\_]); * **DETAIL\_TEXT** - по детальному описанию (можно искать по шаблону   [%\_]); * **SEARCHABLE\_CONTENT** - по содержимому для поиска. Включает в   себя название, описание для анонса и детальное описание (можно искать по   шаблону [%\_]); * **CODE** - по символьному идентификатору (можно искать по   шаблону [%\_]); * **SORT** - по сортировке; * **EXTERNAL\_ID** - по внешнему коду (можно искать по шаблону   [%\_]); * **TIMESTAMP\_X** - по времени изменения; * **DATE\_CREATE** - по времени создания; * **DATE\_ACTIVE\_FROM** - по дате начала активности; * **DATE\_ACTIVE\_TO** - по дате окончанию активности; * **ACTIVE\_DATE** - непустое значение задействует фильтр по датам   активности (*DATE\_ACTIVE\_FROM* и *DATE\_ACTIVE\_TO*). Если   значение не установлено (*""*), фильтрация по датам активности не   производится; * **IBLOCK\_ID** - по коду информационного блока; * **IBLOCK\_CODE** - по символьному коду информационного блока   (можно искать по шаблону [%\_]); * **IBLOCK\_LID** - по языку (можно искать по шаблону [%\_]); * **IBLOCK\_TYPE** - по типу блока (можно искать по шаблону [%\_]); * **IBLOCK\_ACTIVE** - по активности блока (можно искать по шаблону   [%\_]); * **SECTION\_ID** - по родительскому разделу; * **PROPERTY\_<**код свойства> - фильтр по значениям свойств   (можно искать по шаблону [%\_]), для свойств типа "список", поиск будет   осуществляться не по значению перечисления, а по его идентификатору; * **PROPERTY\_<**код свойства>\_VALUE - фильтр по значениям   списка для свойств типа "список" (можно искать по шаблону [%\_]), поиск   будет осуществляться по строковому значению списка, а не по   идентификатору; * **CATALOG\_<CATALOG\_FIELD>\_<PRICE\_TYPE>** - по полю   *CATALOG\_FIELD* из цены типа *PRICE\_TYPE* (ID типа цены), где   *CATALOG\_FIELD* может быть: *PRICE* - цена, *CURRENCY* -   валюта.  Все фильтруемые поля (кроме *SECTION\_ID* и *ACTIVE\_DATE*)могут содержать перед названием [тип проверки фильтра](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=2683), а поля *SECTION\_ID*и *ACTIVE\_DATE* могут содержать перед названием тип проверки фильтра "!" - не равно.  *Значения фильтра* - одиночное значение или массив.  Необязательный. По умолчанию - пустой массив. Полный список полей фильтра и дополнительную информацию [смотрите](/api_help/iblock/classes/ciblockelement/getlist.php) в **[CIBlockElement](/api_help/iblock/classes/ciblockelement/index.php)::[GetList()](/api_help/iblock/classes/ciblockelement/getlist.php).** |
| arSelect | Массив возвращаемых полей элемента. Список полей элемента, а также можно сразу выводить значения его свойств. Для этого в качестве одного из полей необходимо указать *PROPERTY\_<PROPERTY\_CODE>*, где *PROPERTY\_CODE* - ID или символьный код. В результате будет выведены значения свойств элемена в виде полей:  * *PROPERTY\_<PROPERTY\_CODE>\_VALUE* - значение; * *PROPERTY\_<PROPERTY\_CODE>\_ID* - код значения у   элемента; * *PROPERTY\_<PROPERTY\_CODE>\_ENUM\_ID* - код значения (для   свойств типа список).  При установленном модуле торгового каталога можно выводить и цены элемента. Для этого в качестве одного из полей необходимо указать *CATALOG\_GROUP\_<PROPERTY\_CODE>*, где *PROPERTY\_CODE* - ID типа цены.  По умолчанию выводятся все [поля элемента](/api_help/iblock/fields.php#felement). |
| arGroupBy | Массив полей для группировки элемента.  Если поля указаны, то выборка по ним группируется, а в результат добавляется поле *CNT* - количество сгруппированных элементов.  Если указать в качестве arGroupBy пустой массив, то функция вернет количество элементов CNT по заданному фильтру.  Группировать можно по полям элемента, а также по значениям его свойств. Для этого в качестве одного из полей группировки необходимо указать *PROPERTY\_<PROPERTY\_CODE>*, где PROPERTY\_CODE - ID или символьный код свойства.  Необязательное. По умолчанию false - записи не группируются. |

### Смотрите также

* [CIBlockElement](/api_help/iblock/classes/ciblockelement/index.php)::[GetList()](/api_help/iblock/classes/ciblockelement/getlist.php)
* [Поля элементов информационного
  блока](/api_help/iblock/fields.php#felement)
* [Функция GetIBlockElementList](/api_help/iblock/functions/getiblockelementlist.php)

### Примеры использования

```
<?
if(CModule::IncludeModule("iblock"))
{
	// выберем 15 элементов типа "news" из информационного блока "company_news"
	$items = GetIBlockElementListEx("news", "company_news", Array(), 
		Array("DATE_ACTIVE_FROM"=>"DESC", "SORT"=>"ASC", "NAME" => "ASC"), 15);
	// постраничная навигация
	$items->NavPrint("Новости компании");
	// цикл по всем новостям
	while($arItem = $items->GetNext())
	{
		// выведем ссылку на страницу с детальным просмотром
		echo "<a href='".$arItem["DETAIL_PAGE_URL"]."'>".$arItem["NAME"]."</a>";
		// выведем дату
		echo $arItem["DATE_ACTIVE_FROM"]."<br>";
		// выведем картинку для анонса, с ссылкой на детальный просмотр
		echo ShowImage($arItem["PREVIEW_PICTURE"], 100, 100, 
			"border='0'", $arItem["DETAIL_PAGE_URL"]);
		// выведем анонс
		echo $arItem["PREVIEW_TEXT"]."<hr>";
	}
	$items->NavPrint("Новости компании");
}
?>
Копировать
```

  
  

```
<?
// Например, если необходимо вывести новости за сегодняшнюю дату (DATE_ACTIVE_FROM >= сегодня):
$items = GetIBlockElementListEx("news", Array(), Array(), 
	Array("SORT"=>"ASC", "ID" => "DESC"), 15,
	Array(">=DATE_ACTIVE_FROM"=>
		date($DB->DateFormatToPHP(CSite::GetDateFormat("SHORT")))));
// если необходимо вывести все вчерашние новости, т.е.
// (DATE_ACTIVE_FROM >= вчера && DATE_ACTIVE_FROM < сегодня):
$items = GetIBlockElementListEx("news", Array(), Array(), 
	Array("SORT"=>"ASC", "ID" => "DESC"), 15,
	Array(">=DATE_ACTIVE_FROM"=>
		date($DB->DateFormatToPHP(CSite::GetDateFormat("SHORT")), 
			mktime(0,0,0,date("m"),date("d")-1,date("Y"))),
                                      "<DATE_ACTIVE_FROM"=>
		date($DB->DateFormatToPHP(CSite::GetDateFormat("SHORT")), 
			mktime(0,0,0,date("m"),date("d"),date("Y")))));
// если необходимо вывести все новости за 1 января 2003г., т.е.
// (DATE_ACTIVE_FROM >= 01.01.2003 && DATE_ACTIVE_FROM < 02.01.2003):
$items = GetIBlockElementListEx("news", Array(), Array(), 
	Array("SORT"=>"ASC", "ID" => "DESC"), 15,
	Array(">=DATE_ACTIVE_FROM"=>
		date($DB->DateFormatToPHP(CSite::GetDateFormat("SHORT")), 
			mktime(0,0,0,1,1,2003)),
		"<DATE_ACTIVE_FROM"=>
		date($DB->DateFormatToPHP(CSite::GetDateFormat("SHORT")), 
			mktime(0,0,0,1,2,2003))));
?>Копировать
```

Новинки документации в соцсетях: