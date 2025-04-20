[Опросы, голосования](/api_help/vote/index.php)

[Функции](/api_help/vote/function/index.php)

ShowCurrentVote (3.0.1)

ShowCurrentVote
===============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
ShowCurrentVote(
	GROUP_SYMBOLIC_NAME, 
	[
		lid
	]
);Копировать
```

Функция выводит HTML-код текущего опроса группы.

#### Параметры функции

| Параметр | Описание | С версии |
| --- | --- | --- |
| GROUP\_SYMBOLIC\_NAME | Символическое имя группы. | Удален с 4.0.0 |
| lid | ID сайта. Необязательный параметр. По умолчанию - текущий (константа LANG). | Удален с 4.0.0 |
| group\_sid |  | 4.0.0 |
| site\_id | ID сайта. Необязательный параметр. По умолчанию - текущий (SITE\_ID). | 4.0.0 |

### Примеры использования

```
Файл в публичной части сайта - "vote_current.php":
<?
require_once($_SERVER["DOCUMENT_ROOT"]."/bitrix/modules/main/include/prolog_before.php");
// Отображает форму текущего опроса заданной группы,
// после голосования перенаправляет на файл отображающий результат опроса
if (CModule::IncludeModule("vote") && $VOTING_OK=="Y") 
{
	$VOTE_DIR = COption::GetOptionString("vote", "VOTE_DIR", "");
	$z = CLang::GetByID(LANG);
	$zr = $z->Fetch();
	$LANG_DIR = $zr["DIR"];
	$LANG_DIR = TrimExAll($LANG_DIR,"/");
	$VOTE_DIR = TrimExAll($VOTE_DIR,"/");
	LocalRedirect("/".$LANG_DIR."/".$VOTE_DIR."/vote_result.php?VOTE_ID=".$PUBLIC_VOTE_ID."&VOTING_OK=Y");
}
if (strlen($APPLICATION->GetTitle())<=0) $APPLICATION->SetTitle(GetMessage("VOTE_VOTING_TITLE"));
require_once ($_SERVER["DOCUMENT_ROOT"]."/bitrix/modules/main/include/prolog_after.php");
?><?
if (CModule::IncludeModule("vote")) ShowCurrentVote("ANKETA");
require_once ($_SERVER["DOCUMENT_ROOT"]."/bitrix/modules/main/include/epilog.php");
?>Копировать
```

Новинки документации в соцсетях: