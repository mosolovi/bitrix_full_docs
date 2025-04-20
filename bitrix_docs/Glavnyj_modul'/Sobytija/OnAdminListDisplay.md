[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnAdminListDisplay (с версии 9.5.10)

OnAdminListDisplay
==================

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
void
Handler(
	object &list
);Копировать
```

Событие OnAdminListDisplay вызывается в функции [CAdminList::Display()](/api_help/main/general/admin.section/classes/cadminlist/display.php) при выводе в административном разделе списка элементов. Событие позволяет модифицировать объект списка, в частности, добавить произвольные групповые действия над элементами списка, добавить команды в меню действий элемента списка и т.п.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| list | Ссылка на объект класса [CAdminList](/api_help/main/general/admin.section/classes/cadminlist/index.php). |

#### Возвращаемое значение

Возвращаемое значение не используется.

#### Смотрите также

* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)
* [Класс CAdminListRow](/api_help/main/general/admin.section/classes/cadminlistrow/index.php)

### Примеры использования

```
<?
AddEventHandler("main", "OnAdminListDisplay", "MyOnAdminListDisplay");
public static function MyOnAdminListDisplay(&$list)
{
	//add custom group action
	if($list->table_id == "tbl_posting")
		$list->arActions["status_draft"] = "Статус: Черновик";
}
//process custom action
AddEventHandler("main", "OnBeforeProlog", "MyOnBeforeProlog");
public static function MyOnBeforeProlog()
{
	if($_SERVER["REQUEST_METHOD"] == "POST" && $_POST["action"] == "status_draft" && is_array($_POST["ID"]) && $GLOBALS["APPLICATION"]->GetCurPage() == "/bitrix/admin/posting_admin.php")
	{
		if($GLOBALS["APPLICATION"]->GetGroupRight("subscribe") == "W" && check_bitrix_sessid())
		{
			if(CModule::IncludeModule("subscribe"))
			{
				$cPosting = new CPosting;
				foreach($_POST["ID"] as $ID)
					if(($ID = intval($ID)) > 0)
						$cPosting->ChangeStatus($ID, "D");
			}
		}
	}
}
?>Копировать
```

Новинки документации в соцсетях: