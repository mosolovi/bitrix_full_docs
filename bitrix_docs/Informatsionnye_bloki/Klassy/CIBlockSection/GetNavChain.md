[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockSection](/api_help/iblock/classes/ciblocksection/index.php)

GetNavChain (доступен с 3.0.4)

GetNavChain
===========

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
CIBlockResult CIBlockSection::GetNavChain(
	int IBLOCK_ID,
	int SECTION_ID,
	array arSelect = array(),
	$arrayResult = false
);Копировать
```

Метод возвращает путь по дереву от корня до раздела *SECTION\_ID* (пользовательские поля не возвращаются). Метод статический.

#### Параметры вызова

| Параметр | Описание | С версии |
| --- | --- | --- |
| IBLOCK\_ID | Код информационного блока, служит для проверки что раздел *SECTION\_ID*, находится в заданном информационном блоке. Если значение *IBLOCK\_ID* ноль, то проверка не будет выполнена и код информационного блока не будет учитываться. |  |
| SECTION\_ID | Код раздела информационного раздела, путь до которого будет выбран. |  |
| arSelect | Массив возвращаемых полей раздела. Необязательный параметр. По умолчанию будут возвращены все доступные поля. | 12.5.0 |
| arResult | Необязательный параметр. По умолчанию - *false*. Если передать в него *true* - вернет массив элементов, описывающих позиции, а не CDBResult. Это производительнее. | 12.5.0 |

#### Возвращаемое значение

Возвращается объект [CIBlockResult](/api_help/iblock/classes/ciblockresult/index.php) с полями [раздела информационного блока.](/api_help/iblock/fields.php#fiblocksection)

### Примеры использования

```
<?
$nav = CIBlockSection::GetNavChain(false, $SECTION_ID);
while($nav->ExtractFields("nav_")):
?> &raquo; 
	<?if($SECTION_ID == $nav_ID):?>
		<?echo $nav_NAME?>
	<?else:?>
		<a class="navchain" href="<?=$application->getcurpage()?>?iblock_id=<?=$iblock_id?>§ion_id=<?=$nav_id?>#tb"><?echo $nav_NAME?></a>
	<?endif?>
<?endwhile;?>Копировать
```

Показать полный массив данных:

```
$list = CIBlockSection::GetNavChain(false,$Section['ID'], array(), true);
foreach ($list as $arSectionPath){
	echo '<pre>';print_r($arSectionPath);echo '</pre>';
}Копировать
```

#### Смотрите также

* [CIBlockResult](/api_help/iblock/classes/ciblockresult/index.php)
* [Поля раздела информационного блока](/api_help/iblock/fields.php#fiblocksection)

Новинки документации в соцсетях: