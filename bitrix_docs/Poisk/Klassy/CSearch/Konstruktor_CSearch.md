[Поиск](/api_help/search/index.php)

[Классы](/api_help/search/classes/index.php)

[CSearch](/api_help/search/classes/csearch/index.php)

Конструктор CSearch (доступен с 3.0.4)

Конструктор CSearch
===================

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
CDBResult
CSearch(
	string strQuery,
	string LID = false,
	string MODULE_ID = false,
	string ITEM_ID = false,
	string PARAM1 = false,
	string PARAM2 = false,
	array aSort = array(),
	array aParamsEx = array(),
	bool bTagsCloud = false
);Копировать
```

Конструктор класса CSearch возвращает записи индекса, которые удовлетворяют заданной строке запроса и указанным параметрам, а так же доступны на просмотр для текущего посетителя (в соответствии с его уровнем доступа).

**Примечание:** метод устарел, лучше воспользоваться методом [CSearch::Search](/api_help/search/classes/csearch/search.php). Это показано в приведенном ниже примере.

#### Смотрите также

* [CSearch::Search](/api_help/search/classes/csearch/search.php)

### Примеры использования

```
<?
$q = "жареная рыба или селедка";
$module_id = "forum";
//Эту строку заменяем
//$obSearch = new CSearch($q, LANG, $module_id);
// на следующую:
$obSearch = new CSearch;
$obSearch->Search(array(
	"QUERY" => $q,
	"SITE_ID" => LANG,
	"MODULE_ID" => $module_id,
));
if ($obSearch->errorno!=0):
	?>
	<font class="text">В поисковой фразе обнаружена ошибка:</font>
	<?echo ShowError($obSearch->error);?>
	<font class="text">Исправьте поисковую фразу и повторите поиск.</font>
	<?
else:
	while($arResult = $obSearch->GetNext())
	{
	?>
		<a href="<?echo $arResult["URL"]?>"><?echo $arResult["TITLE_FORMATED"]?></a>
		<?echo $arResult["BODY_FORMATED"]?>
		<hr size="1" color="#DFDFDF">
	<?
	}
endif;
?>
Копировать
```

Новинки документации в соцсетях: