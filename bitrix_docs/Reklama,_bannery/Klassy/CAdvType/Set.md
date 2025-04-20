[Реклама, баннеры](/api_help/advertising/index.php)

[Классы](/api_help/advertising/classes/index.php)

[CAdvType](/api_help/advertising/classes/cadvtype/index.php)

Set (3.3.4)

Set
===

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
varchar(255)
CAdvType::Set(
	array arFields,
	varchar(255) TYPE_SID="",
	char(1) CHECK_RIGHTS="Y"
);Копировать
```

Метод создает новый тип баннеров, либо модифицирует существующий в случае указания во втором параметре символьного ID типа. Возвращает ID созданного типа, либо ID модифицированного типа. Метод нестатический.

#### Параметры метода

| Параметры | Описание |
| --- | --- |
| arFields | Массив параметров контракта. В массиве допустимы следующие индексы:  * SID - символьный ID типа (используется в публичной части при выводе баннеров по типу) * ACTIVE - флаг активности: "Y" - тип активен; "N" - тип не активен; * NAME - имя типа * DESCRIPTION - описание типа * SORT - порядок сортировки типа в списках |
| TYPE\_SID | ID типа, если не указывать - создаётся новый тип. |
| CHECK\_RIGHTS | Флаг необходимости проверки прав текущего пользователя: "Y" - необходимо проверить права текущего пользователя; "N" - тип создавать и модифицировать независимо от прав текущего пользователя. Необязательный параметр. |

### Примеры использования

```
<!-- Пример кода, добавляющего новый контракт
либо модифицирующего существующий: -->
<?
if ((strlen($save)>0 || strlen($apply)>0) && $REQUEST_METHOD=="POST")
{
	$arFields = array(
		"SID"			   => $SID,
		"ACTIVE"			=> $ACTIVE,
		"SORT"			  => $SORT,
		"NAME"			  => $NAME,
		"DESCRIPTION"	   => $DESCRIPTION
	);
	if ($SID = CAdvType::Set($arFields, $OLD_SID))
	{
		if (strlen($strError)<=0)
		{
			if (strlen($save) > 0)
				LocalRedirect("adv_type_list.php?lang=".LANG); 
			else
				LocalRedirect("adv_type_edit.php?SID=".$SID."&lang=".LANG);
		}
	}
	$DB->PrepareFields("b_adv_type");
}
?>Копировать
```

Новинки документации в соцсетях: