[Опросы, голосования](/api_help/vote/index.php)

[Функции](/api_help/vote/function/index.php)

IsUserVoted (3.0.1)

IsUserVoted
===========

```
IsUserVoted (VOTE_ID)Копировать
```

Функция возвращает true, если пользователь уже голосовал по заданному опросу и ему больше нельзя голосовать в соответствии с настройками опроса, в противном случае - false

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| VOTE\_ID | ID опроса. |

#### Примеры использования

```
Файл в публичной части сайта - "vote_now.php":
<?
// Отображает форму текущего опроса группы, если пользователь
// ещё не голосовал, иначе отображает результаты текущего опроса группы
require_once($_SERVER["DOCUMENT_ROOT"]."/bitrix/modules/main/include/prolog_before.php");
if (CModule::IncludeModule("vote"))
{
	$VID = GetCurrentVote("ANKETA");
	if ($VOTING_OK=="Y" || IsUserVoted($VID)) $ALREADY_VOTED = "Y"; else $ALREADY_VOTED = "N";
}
if (strlen($APPLICATION->GetTitle())<=0) $APPLICATION->SetTitle(GetMessage("VOTE_VOTING_TITLE"));
require_once ($_SERVER["DOCUMENT_ROOT"]."/bitrix/modules/main/include/prolog_after.php");
?><?
if (CModule::IncludeModule("vote")) 
{
	if ($ALREADY_VOTED=="Y") ShowVoteResults($VID); else ShowVote($VID);
}
require_once ($_SERVER["DOCUMENT_ROOT"]."/bitrix/modules/main/include/epilog.php");
?>Копировать
```

Новинки документации в соцсетях: