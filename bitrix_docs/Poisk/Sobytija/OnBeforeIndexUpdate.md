[Поиск](/api_help/search/index.php)

[События](/api_help/search/events/index.php)

OnBeforeIndexUpdate (доступен с 8.0.4)

OnBeforeIndexUpdate
===================

```
void
функция-обработчик(
	int ID,
	array arFields
);Копировать
```

Событие "OnBeforeIndexUpdate" вызывается перед обновлением поискового индекса.

#### Параметры

| Параметр | Описание |
| --- | --- |
| ID | Уникальный идентификатор записи в поисковом индексе. |
| arFields | Поля поискового индекса. |

#### Смотрите также

* [Обработка событий](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

#### Пример функции-обработчика:

```
<?
// регистрируем обработчик события "OnBeforeIndexUpdate" модуля "search"
RegisterModuleDependences("search", "OnBeforeIndexUpdate", "my_module", "CMyModule", "AddSearchExtData");
// создаем в модуле my_module в классе CMyModule функцию-метод AddSearchExtData
public static function AddSearchExtData($ID, $arFields)
{
	global $DB;
	if($arFields["MODULE_ID"]=="my_module")
		$DB->Add("my_search_ext_data", array("SEARCH_CONTENT_ID"=>$ID, "EXT_DATA"=>time()));
}
?>Копировать
```

```
AddEventHandler("search", "OnBeforeIndexUpdate", "OnBeforeIndexUpdate");
function OnBeforeIndexUpdate($ID, $arFields)
{
	AddMessage2Log("
======1111111111111111111111111111111111111============
", LOG_FILENAME);
	AddMessage2Log("
" . print_r($arFields, true) . "
", LOG_FILENAME);
	AddMessage2Log("
" . print_r($ID, true) . "
", LOG_FILENAME);
  
}Копировать
```

Новинки документации в соцсетях: