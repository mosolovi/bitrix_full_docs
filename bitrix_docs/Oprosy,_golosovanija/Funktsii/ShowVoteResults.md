[Опросы, голосования](/api_help/vote/index.php)

[Функции](/api_help/vote/function/index.php)

ShowVoteResults (3.0.1)

ShowVoteResults
===============

```
ShowVoteResults(
	VOTE_ID, 
	[
		template
	]
);Копировать
```

Функция выводит HTML-код с диаграммой результатов опроса.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| VOTE\_ID | ID опроса. |
| template | Имя файла - шаблона для показа результатов опроса. По умолчанию будет использован шаблон, заданный в параметрах опроса. Необязательный параметр. |

#### Примеры использования

```
Файл в публичной части сайта - "vote_result.php":
<?
// Отображает результат опроса по заданному ID
require_once($_SERVER["DOCUMENT_ROOT"]."/bitrix/modules/main/include/prolog_before.php");
if (strlen($APPLICATION->GetTitle())<=0) $APPLICATION->SetTitle(GetMessage("VOTE_RESULTS_TITLE"));
//$APPLICATION->AddChainItem(GetMessage("VOTE_VOTES_LIST"), "vote_list.php");
require_once ($_SERVER["DOCUMENT_ROOT"]."/bitrix/modules/main/include/prolog_after.php");
?><?
if (CModule::IncludeModule("vote")) ShowVoteResults($VOTE_ID);
require_once ($_SERVER["DOCUMENT_ROOT"]."/bitrix/modules/main/include/epilog.php");
?>Копировать
```

Новинки документации в соцсетях: