[Опросы, голосования](/api_help/vote/index.php)

[Функции](/api_help/vote/function/index.php)

GetVoteList (3.0.1)

GetVoteList
===========

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
GetVoteList([
	GROUP_SYMBOLIC_NAME,
	params, 
	site_id = SITE_ID
);Копировать
```

Функция возвращает выборку из базы по опросам.

#### Параметры функции

Массив параметров для выборки, возможные параметры:

| Параметр | Описание | С версии |
| --- | --- | --- |
| GROUP\_SYMBOLIC\_NAME | Строка или массив символических имён групп каналов. |  |
| params | * **order** SQL код, содержащий параметры сортировки для выборки. Необязательный параметр. По умолчанию: "ORDER BY C.C\_SORT, C.ID, V.DATE\_START desc" * **bDescPageNumbering** Обратная постраничная навигация. По умолчанию false. * **nPageSize** Размер страницы * **bShowAll** Разрешить показать все. По умолчанию false. * **nTopCount** - Ограничение числа верхних записей. * **bCount** Вернуть только количество. По умолчанию true. |  |
| lid | ID сайта. По умолчанию - текущий (константа LANG). |  |
| site\_id | ID сайта. По умолчанию - текущий - SITE\_ID. Необязательный параметр. | 4.0.0 |
| group\_sid | Необязательный параметр. Значение по умолчанию - "". | 4.0.0 |

### Примеры использования

```
Файл в публичной части сайта - "vote_list.php":
<?
// Отображает список опросов (архив)
require_once($_SERVER["DOCUMENT_ROOT"]."/bitrix/modules/main/include/prolog_before.php");
if (CModule::IncludeModule("vote")) require_once($_SERVER["DOCUMENT_ROOT"]."/bitrix/modules/vote/include.php");
if (strlen($APPLICATION->GetTitle())<=0) $APPLICATION->SetTitle(GetMessage("VOTE_LIST_TITLE"));
require_once ($_SERVER["DOCUMENT_ROOT"]."/bitrix/modules/main/include/prolog_after.php");
?><?
if (CModule::IncludeModule("vote"))
{ 
	$votes = GetVoteList(); // список опросов
	require_once ($_SERVER["DOCUMENT_ROOT"]."/bitrix/php_interface/include/vote/list/default.php"); // шаблон показа
}
require_once ($_SERVER["DOCUMENT_ROOT"]."/bitrix/modules/main/include/epilog.php");
?>Копировать
```

```
<?
// вывод всех активных опросов на текущем сайте, отсортированных в следующем порядке: по индексу сортировки канала, ID канала, индексу сортировки опроса, времени начала опроса. Активный опрос в
// данном контексте - это опрос, у которого атрибут ACTIVE установлен в Y, а время начала голосования меньше текущего.
require_once($_SERVER["DOCUMENT_ROOT"]."/bitrix/modules/main/include/prolog_before.php");
$APPLICATION->SetTitle("Результаты опроса");
$APPLICATION->AddChainItem("Архив опросов", "vote_list.php");
require_once($_SERVER["DOCUMENT_ROOT"]."/bitrix/modules/main/include/prolog_after.php");
if (CModule::IncludeModule("vote"))
{
	$db_res = GetVoteList("");
	if (!!$db_res)
	{
		if (!empty($arResult["NAV_STRING"]))
		{
			?>;<div class="vote-navigation-box vote-navigation-top">
				<div class="vote-page-navigation">
					<?=$arResult["NAV_STRING"]?>
				</div><div class="vote-clear-float"></div>
			</div><?
		}
		?><ol class="vote-items-list voting-list-box"><?
		while ($arVote = $db_res->Fetch()) {
		?><li class="vote-item-vote <?
			?><?=($arVote["LAMP"]=="green" ? "vote-item-vote-active " : ($arVote["LAMP"]=="red" ? "vote-item-vote-disable " : ""))?>">
			<div class="vote-item-header"><?
				if (!empty($arVote["TITLE"])) { ?><span class="vote-item-title"><?=$arVote["TITLE"];?></span><? }?>
				<div class="vote-clear-float"></div>
			</div>
			<?
			$arDateBlocks = array();
			if (!!$arVote["DATE_START"])
				$arDateBlocks[] = '<span class="vote-item-date-start">'.FormatDate($DB->DateFormatToPHP(CSite::GetDateFormat('FULL')), MakeTimeStamp($arVote["DATE_START"])).'</span>';
			if (!!$arVote["DATE_END"] && $arVote["DATE_END"] != "31.12.2030 23:59:59")
				$arDateBlocks[] = '<span class="vote-item-date-end">'.FormatDate($DB->DateFormatToPHP(CSite::GetDateFormat('FULL')), MakeTimeStamp($arVote["DATE_END"])).'</span>';
			if (!empty($arDateBlocks)) {
				?><div class="vote-item-date"> - </span>', $arDateBlocks)?></div><?
			}
			if ($arVote["COUNTER"] > 0)
			{
				?&qt;<div class="vote-item-counter"><span>Голосов:</span> <?=$arVote["COUNTER"]?></div><?
			}
			if (!empty($arVote["IMAGE"]) || !empty($arVote["DESCRIPTION"])):
			?>
			<div class="vote-item-footer">
				<?if (!empty($arVote["IMAGE"])):?>
				<div class="vote-item-image">
					<img src="" width="<?=$arVote["IMAGE"]["WIDTH"]?>" height="<?=$arVote["IMAGE"]["HEIGHT"]?>" border="0" />
				</div>
				<?endif;
				if (!empty($arVote["DESCRIPTION"])):?>
				<div class="vote-item-description"><?=$arVote["DESCRIPTION"];?></div>
				<?endif?>
				<div class="vote-clear-float"></div>
			</div>
			<?
			endif;
			?>
			
		<?
		}
	?><?
	}
}
?><style>
	ol.vote-items-list, ol.vote-items-list li {
		margin: 0; padding: 0; border: none; font-size: 100%; list-style-type: none;}
	ol.vote-items-list li {
		padding: 0.55em;
		border: 1px solid #ccc;
		border-top: none;}
	ol.vote-items-list li:first-child { border-top: 1px solid #ccc; }
	.vote-item-title { font-weight:bold; }
	div.vote-item-date { font-style: italic; }
	div.vote-item-header { margin-bottom: 0.5em; }
	div.vote-item-footer { margin-top: 0.5em; }
	div.vote-item-image { float:left; padding-right:0.55em; }
	div.vote-clear-float { clear: both; }
</style><?
require_once ($_SERVER["DOCUMENT_ROOT"]."/bitrix/modules/main/include/epilog.php");
?>Копировать
```

Новинки документации в соцсетях: