[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumGroup](/api_help/forum/developer/cforumgroup/index.php)

Add (доступен с 3.3.3)

Add
===

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
int
Add(
	array arFields
);>Копировать
```

Создает новую группу с параметрами, указанными в массиве *arFields*. Возвращает код созданной группы. На добавление нового звания параметры посетителей форума не пересчитываются. Пересчет будт происходить постепенно по мере общения посетителей на форуме. Метод статический.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| arFields | Массив вида Array(*field1*=>*value1*[, *field2*=>*value2* [, ..]]), где    *field* - название поля;  *value* - значение поля.   Поля перечислены в [списке полей групп](/api_help/forum/fields.php#cforumgroup). В специальное поле "LANG" заносится массив массивов полей языковых параметров групп, которые имеют аналогичную структуру. |

#### Возвращаемое значение

Возвращает код созданной группы. В случае ошибки добавления возвращает False.

#### Смотрите также

* [Поля группы](/api_help/forum/fields.php#cforumgroup)

### Примеры использования

```
<?
$arFields = array("SORT" => $SORT);
$arSysLangs = array("ru", "en");
for ($i = 0; $i<count($arSysLangs); $i++)
{
	$arFields["LANG"][] = array(
		"LID" => $arSysLangs[$i],
		"NAME" => ${"NAME_".$arSysLangs[$i]},
		"DESCRIPTION" => ${"DESCRIPTION_".$arSysLangs[$i]}
	);
}
$ID = CForumGroup::Add($arFields);
if (IntVal($ID)<=0)
	echo "Error!";
?>Копировать
```

Новинки документации в соцсетях: