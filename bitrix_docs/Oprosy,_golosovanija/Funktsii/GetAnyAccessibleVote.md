[Опросы, голосования](/api_help/vote/index.php)

[Функции](/api_help/vote/function/index.php)

GetAnyAccessibleVote (3.0.1)

GetAnyAccessibleVote
====================

```
GetAnyAccessibleVote([lid])Копировать
```

Функция возвращает ID первого попавшегося опроса по которому пользователь ещё не голосовал, с учётом прав пользователя, у которого должно быть право "на участие в опросе" (>=2)

#### Параметры функции

| Параметр | Описание | С версии |
| --- | --- | --- |
| lid | Сайт группы опросов. По умолчанию - текущий (константа LANG). Необязательный параметр. | Удален с 4.0.0 |
| site\_id | Сайт группы опросов. Необязательный параметр. | 4.0.0 |
| channel\_id | Необязательный параметр. Значение по умолчанию - "null". | 10.0.1 |

#### Примеры использования

```
Файл в публичной части сайта - "vote_any.php":
<?
require_once($_SERVER["DOCUMENT_ROOT"]."/bitrix/modules/main/include/prolog_before.php");
// Отображает форму первого попавшегося опроса по которому пользователь ещё не голосовал
// если пользователь проголосовал, то перенаправляет его на файл отображающий результат данного опроса
if (CModule::IncludeModule("vote") && $VOTING_OK=="Y") 
{
	$VOTE_DIR = COption::GetOptionString("vote", "VOTE_DIR", "");
	$z = CLang::GetByID(LANG);
	$zr = $z->Fetch();
	$LANG_DIR = $zr["DIR"];
	$LANG_DIR = TrimExAll($LANG_DIR,"/");
	$VOTE_DIR = TrimExAll($VOTE_DIR,"/");
	LocalRedirect("/".$LANG_DIR."/".$VOTE_DIR."/vote_result.php?VOTE_ID=". $PUBLIC_VOTE_ID."&VOTING_OK=".$VOTING_OK);
}
if (strlen($APPLICATION->GetTitle())<=0) $APPLICATION->SetTitle(GetMessage("VOTE_VOTING_TITLE"));
require_once ($_SERVER["DOCUMENT_ROOT"]."/bitrix/modules/main/include/prolog_after.php");
?><?
if (CModule::IncludeModule("vote")) 
{
	$VID = GetAnyAccessibleVote();
	ShowVote($VID);
}
require_once ($_SERVER["DOCUMENT_ROOT"]."/bitrix/modules/main/include/epilog.php");
?>Копировать
```

Новинки документации в соцсетях: