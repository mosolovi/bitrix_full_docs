[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnBuildGlobalMenu (с версии 6.0.3)

OnBuildGlobalMenu
=================

```
функция-обработчик Копировать
```

#### Пример функции-обработчика

```
public static function OnBuildGlobalMenu(&$aGlobalMenu, &$aModuleMenu)
{
	global $USER;
	if(!$USER->IsAdmin())
		return;
	$aMenu = array(
		"parent_menu" => "global_menu_content",
		"section" => "clouds",
		"sort" => 150,
		"text" => GetMessage("CLO_STORAGE_MENU"),
		"title" => GetMessage("CLO_STORAGE_TITLE"),
		"url" => "clouds_index.php?lang=".LANGUAGE_ID,
		"icon" => "clouds_menu_icon",
		"page_icon" => "clouds_page_icon",
		"items_id" => "menu_clouds",
		"more_url" => array(
			"clouds_index.php",
		),
		"items" => array()
	);
	$rsBuckets = CCloudStorageBucket::GetList(array("SORT"=>"DESC", "ID"=>"ASC"));
	while($arBucket = $rsBuckets->Fetch())
	$aMenu["items"][] = array(
		"text" => $arBucket["BUCKET"],
		"url" => "clouds_file_list.php?lang=".LANGUAGE_ID."&bucket=".$arBucket["ID"]."&path=/",
		"more_url" => array(
		"clouds_file_list.php?bucket=".$arBucket["ID"],
		),
		"title" => "",
		"page_icon" => "clouds_page_icon",
		"items_id" => "menu_clouds_bucket_".$arBucket["ID"],
		"module_id" => "clouds",
		"items" => array()
	);
	if(!empty($aMenu["items"]))
		$aModuleMenu[] = $aMenu;
}Копировать
```

Новинки документации в соцсетях: