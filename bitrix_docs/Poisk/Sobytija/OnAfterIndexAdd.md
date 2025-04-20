[Поиск](/api_help/search/index.php)

[События](/api_help/search/events/index.php)

OnAfterIndexAdd (доступен с 8.0.4)

OnAfterIndexAdd
===============

Включить вкладки

Описание и параметры

Пример функции-обработчика

### Описание и параметры

```
void
функция-обработчик(
	int ID,
	array arFields
);Копировать
```

Событие "OnAfterIndexAdd" вызывается после добавления новых данных в поисковый индекс.

#### Параметры

| Параметр | Описание |
| --- | --- |
| ID | Уникальный идентификатор записи в поисковом индексе. |
| arFields | Поля поискового индекса. |

#### Смотрите также

* [Обработка событий](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Пример функции-обработчика

```
<?
// регистрируем обработчик события "OnAfterIndexAdd" модуля "search"
RegisterModuleDependences("search", "OnAfterIndexAdd", "my_module", "CMyModule", "AddSearchExtData");
// создаем в модуле my_module в классе CMyModule функцию-метод AddSearchExtData
public static function AddSearchExtData($ID, $arFields)
{
	global $DB;
	if($arFields["MODULE_ID"]=="my_module")
		$DB->Add("my_search_ext_data", array("SEARCH_CONTENT_ID"=>$ID, "EXT_DATA"=>time()));
}
?>Копировать
```

Новинки документации в соцсетях: