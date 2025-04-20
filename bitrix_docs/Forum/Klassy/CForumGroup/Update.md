[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumGroup](/api_help/forum/developer/cforumgroup/index.php)

Update (доступен с 3.3.3)

Update
======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
int
Update(
	int ID,
	array arFields
);Копировать
```

Изменяет параметры существующей группы с кодом *ID* на параметры, указанные в массиве *arFields*. Возвращает код изменяемой группы. Метод статический.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| ID | Код группы, параметры которой необходимо изменить. |
| arFields | Массив вида Array(*field1*=>*value1*[, *field2*=>*value2* [, ..]]), где    *field* - название поля;  *value* - значение поля.   Поля перечислены в [списке полей групп](/api_help/forum/fields.php#cforumgroup). В специальное поле "LANG" заносится массив массивов полей языковых параметров групп, которые имеют аналогичную структуру. |

#### Возвращаемое значение

Возвращает код измененной группы. В случае ошибки изменения возвращает False.

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
$ID1 = CForumGroup::Update($ID, $arFields);
if (IntVal($ID1)<=0)
	echo "Error!";
?>Копировать
```

Новинки документации в соцсетях: