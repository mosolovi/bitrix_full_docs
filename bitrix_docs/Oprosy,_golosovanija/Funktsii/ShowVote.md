[Опросы, голосования](/api_help/vote/index.php)

[Функции](/api_help/vote/function/index.php)

ShowVote (3.0.1)

ShowVote
========

```
ShowVote(
	VOTE_ID, 
	[
		template
	]
);Копировать
```

Функция выводит HTML-код формы опроса.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| VOTE\_ID | ID опроса. |
| template | Имя файла - шаблона для показа опроса. По умолчанию будет использован шаблон, заданный в параметрах опроса. Необязательный параметр. |

#### Примеры использования

```
Файл в публичной части сайта - "vote.php":
<?
// Отображает форму опроса по заданному ID
require_once($_SERVER["DOCUMENT_ROOT"]."/bitrix/modules/main/include/prolog_before.php");
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
if (CModule::IncludeModule("vote")) ShowVote($VOTE_ID);
require_once ($_SERVER["DOCUMENT_ROOT"]."/bitrix/modules/main/include/epilog.php");
?>Копировать
```

Новинки документации в соцсетях: