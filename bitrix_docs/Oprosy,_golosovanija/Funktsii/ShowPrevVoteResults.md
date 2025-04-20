[Опросы, голосования](/api_help/vote/index.php)

[Функции](/api_help/vote/function/index.php)

ShowPrevVoteResults (3.0.1)

ShowPrevVoteResults
===================

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
ShowPrevVoteResults (
	GROUP_SYMBOLIC_NAME, 
	[
		level, 
		[
			lid
		]
	]
);Копировать
```

Функция выводит HTML-код диаграммы результатов предыдущего опроса группы.

#### Параметры функции

| Параметр | Описание | С версии |
| --- | --- | --- |
| GROUP\_SYMBOLIC\_NAME | Символическое имя группы. | Удален с 4.0.0 |
| level | Уровень предыдущего опроса (1 - предыдущий, 2 - предпредыдущий и т.д.). По умолчанию - 1. Необязательный параметр. |  |
| lid | ID сайта. По умолчанию - текущий. Необязательный параметр. | Удален с 4.0.0 |
| group\_sid |  | 4.0.0 |
| site\_id | ID сайта. По умолчанию - текущий (SITE\_ID). Необязательный параметр. | 4.0.0 |

### Примеры использования

```
Файл в публичной части сайта - "vote_prev.php":
<?
// Отображает результаты предыдущего опроса заданной группы
require_once($_SERVER["DOCUMENT_ROOT"]."/bitrix/modules/main/include/prolog_before.php");
if (strlen($APPLICATION->GetTitle())<=0) $APPLICATION->SetTitle(GetMessage("VOTE_PREV_VOTING_TITLE"));
$APPLICATION->AddChainItem(GetMessage("VOTE_VOTES_LIST"), "vote_list.php");
require_once ($_SERVER["DOCUMENT_ROOT"]."/bitrix/modules/main/include/prolog_after.php");
?><?
if (CModule::IncludeModule("vote")) ShowPrevVoteResults("ANKETA");
require_once ($_SERVER["DOCUMENT_ROOT"]."/bitrix/modules/main/include/epilog.php");
?>
Копировать
```

Новинки документации в соцсетях: