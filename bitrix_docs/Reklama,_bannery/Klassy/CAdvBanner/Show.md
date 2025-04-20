[Реклама, баннеры](/api_help/advertising/index.php)

[Классы](/api_help/advertising/classes/index.php)

[CAdvBanner](/api_help/advertising/classes/cadvbanner/index.php)

Show (3.3.4)

Show
====

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
text 
CAdvBanner::Show(
	varchar(255)  TYPE_SID,
	text HTML_BEFORE=false,
	text HTML_AFTER=false,
);Копировать
```

Метод выбирает в соответствии с весами (приоритетами) произвольный баннер по указанному типу, фиксирует факт показа баннера в базе данных и возвращает готовый HTML баннера (используется в шаблоне сайта для вывода баннеров). Метод нестатический.

#### Параметры метода

| Параметры | Описание | С версии |
| --- | --- | --- |
| TYPE\_SID | Символьный идентификатор типа. |  |
| HTML\_BEFORE | Необязательный параметр. | 4.0.0 |
| HTML\_AFTER | Необязательный параметр. | 4.0.0 |

### Примеры использования

```
<!-- Пример кода, который может быть использован
в HTML шаблоне сайта для вывода баннера типа "TOP": -->
<?
if (CModule::IncludeModule("advertising")) :
	$s = CAdvBanner::Show("TOP");
	if (strlen($s)>0) :
		// выводим HTML баннера  
		?>
		<table width="0%" border="0" cellspacing="0" cellpadding="0">
			<tr>
				<td align=center><?=$s?></td>
			</tr>
		</table>
		<?
	endif;
endif;
?>Копировать
```

Новинки документации в соцсетях: