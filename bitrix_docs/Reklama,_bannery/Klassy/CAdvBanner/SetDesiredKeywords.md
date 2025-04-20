[Реклама, баннеры](/api_help/advertising/index.php)

[Классы](/api_help/advertising/classes/index.php)

[CAdvBanner](/api_help/advertising/classes/cadvbanner/index.php)

SetDesiredKeywords (3.3.16)

SetDesiredKeywords
==================

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
CAdvBanner::SetDesiredKeywords(
	mixed keywords,
	varchar(255) TYPE_SID=""
);Копировать
```

#### Описание

Метод задает массив желательных ключевых слов для данной страницы. Если одно из ключевых слов баннера (либо контракта, к которому принадлежит баннер) будет найдено в данном массиве, то этот баннер будет показываться на данной странице с более высоким приоритетом. В случае, если не будет найден ни один баннер, отвечающий установленным ключевым словам, то баннер для показа будет выбран из тех, для которых вообще не установлено ни одно ключевое слово. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| keywords | Ключевые слова. Конструкции, которые можно передавать в этом параметре, описаны в примечаниях ниже. |
| TYPE\_SID | Идентификатор типа. В данном параметре вы можете указать тип рекламы для которой будут заданы ключевые слова. Если данный параметр оставить пустым, то ключевые слова будут заданы для всех типов. Необязательный параметр. |

### Примеры использования

Пример использования на конкретной странице:

```
<?
require_once($_SERVER["DOCUMENT_ROOT"]."/bitrix/modules/main/include/prolog_before.php");
if (CModule::IncludeModule("advertising"))
{
	 // желательные ключевые слова с точным совпадением		
	 $arrKeywords = array();
	 $arrKeywords[] = array("EXACT_MATCH" => "Y", "KEYWORD" => "GeForce");
	 $arrKeywords[] = array("EXACT_MATCH" => "Y", "KEYWORD" => "video");
	 CAdvBanner::SetDesiredKeywords($arrKeywords, "LEFT");
	 // желательные ключевые слова с вхождением
	 CAdvBanner::SetDesiredKeywords(array("Ford", "BMW", "Lada"), "RIGHT");
}
$APPLICATION->SetTitle("Заголовок страницы");
require_once($_SERVER["DOCUMENT_ROOT"]."/bitrix/modules/main/include/prolog_after.php");
// тело страницы
require_once($_SERVER["DOCUMENT_ROOT"]."/bitrix/modules/main/include/epilog.php");
?>
Копировать
```

Пример использования для всего сайта, в prolog\_after.php:

```
<?
if (CModule::IncludeModule("advertising"))
{
	CAdvBanner::SetDesiredKeywords($APPLICATION->GetPageProperty("keywords"));
}
?>
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN">
<html>
<head>
</head>
<body>
...
Копировать
```

**Примечания**

Конструкции, которые можно передавать в параметре `keywords`, включают.

1. Массив, состоящий из массивов, каждый из которых имеет ключи:
   * **EXACT\_MATCH** - указывает как искать слово - точное совпадение (Y), либо вхождение (N).
   * **KEYWORDS** - ключевое слово.Пример:  
     

   ```
   Array
   (
   	[0] => Array
   	(
   		[EXACT_MATCH] => Y
   		[KEYWORD] => GeForce
   	)
   	[1] => Array
   	(
   		[EXACT_MATCH] => Y
   		[KEYWORD] => Radeon
   	)
   )
   Копировать
   ```
2. Массив, элементами которого будут являться сами ключевые слова.

   Пример:

     

   ```
   Array
   (
   	[0] => GeForce
   	[1] => Radion
   	[2] => Sony
   )
   Копировать
   ```

   В этом варианте по умолчанию в дальнейшем будет искаться вхождение ключевых слов баннера в данные ключевые слова (либо
   наоборот).
3. Список ключевых слов, разделенных запятой.

   Пример:

     

   ```
   "GeForce, Radion, Sony"
   Копировать
   ```

   В этом варианте по умолчанию в дальнейшем будет также искаться вхождение ключевых слов баннера в данные ключевые слова (либо
   наоборот).

Новинки документации в соцсетях: