[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnChangePermissions (с версии 3.0.3)

OnChangePermissions
===================

Включить вкладки

Описание и параметры

Примеры

### Описание и параметры

```
функция-обработчик(
	array site_path,
	array permissions
);Копировать
```

Событие "OnChangePermissions" вызывается при изменении прав доступа к файлу или папке методом [$APPLICATION->SetFileAccessPermission](/api_help/main/reference/cmain/setfileaccesspermission.php).

#### Параметры

| Параметр | Описание |
| --- | --- |
| *site\_path* | Массив вида: array("идентификатор сайта", "путь к файлу относительно корня этого сайта"). |
| *permissions* | Массив прав доступа. |

#### Смотрите также

* [Событие "OnChangeFile"](/api_help/main/events/onbeforechangefile.php)
* [CMain::SetFileAccessPermission](/api_help/main/reference/cmain/setfileaccesspermission.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Примеры

```
<?
// файл /bitrix/modules/search/classes/mysql/search.php
class CSearch extends CAllSearch
{
	// создаем обработчик события "OnChangePermissions"
	public static function OnChangeFilePermissions($path, $permission)
	{
		CMain::InitPathVars($site, $path);
		$DOC_ROOT = CSite::GetSiteDocRoot($site);
		while(strlen($path)>0 && $path[strlen($path)-1]=="/") //отрежем / в конце, если есть
			$path=substr($path, 0, strlen($path)-1);
		global $APPLICATION, $DB;
		if(file_exists($DOC_ROOT.$path))
		{
			@set_time_limit(300);
			$arGroups = CSearch::GetGroupCached();
			if(is_dir($DOC_ROOT.$path))
			{
				$handle  = @opendir($DOC_ROOT.$path);
				while($file = @readdir($handle))
				{
					if($file == "." || $file == "..") continue;
					if(is_dir($DOC_ROOT.$path."/".$file))
					{
						if($path."/".$file=="/bitrix")
							continue;
					}
					CSearch::OnChangeFilePermissions(Array($site, $path."/".$file), Array());
				}
			}
			else //if(is_dir($DOCUMENT_ROOT.$path))
			{
				$strGPerm = "0";
				for($i=0; $i<count($arGroups); $i++)
				{
					if($arGroups[$i]>1)
					{
						$p = $APPLICATION->GetFileAccessPermission(Array($site, $path), Array($arGroups[$i]));
						if($p>="R")
						{
							$strGPerm .= ",".$arGroups[$i];
							if($arGroups[$i]==2) break;
						}
					}
				}
				$r = $DB->Query("SELECT ID FROM b_search_content WHERE MODULE_ID='main' AND ITEM_ID='".$site."|".$path."'");
				while($arR = $r->Fetch())
					$DB->Query("DELETE FROM b_search_content_group WHERE SEARCH_CONTENT_ID=".$arR["ID"]);
				$strSql =
					"INSERT INTO b_search_content_group(SEARCH_CONTENT_ID, GROUP_ID) ".
					"SELECT S.ID, G.ID ".
					"FROM b_search_content S, b_group G ".
					"WHERE MODULE_ID='main' ".
					"    AND ITEM_ID='".$site."|".$path."' ".
					"    AND G.ID IN (".$strGPerm.") ";
				$DB->Query($strSql);
			} //if(is_dir($DOCUMENT_ROOT.$path))
		}//if(file_exists($DOCUMENT_ROOT.$path))
	}
}
?>Копировать
```

#### Пример регистрации функции-обработчика:

```
<?
// регистрируем обработчик события "OnChangePermissions"
RegisterModuleDependences("main", "OnChangePermissions", "search", "CSearch", "OnChangeFilePermissions");
?>Копировать
```

Новинки документации в соцсетях: