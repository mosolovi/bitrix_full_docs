[Поиск](/api_help/search/index.php)

[События](/api_help/search/events/index.php)

OnSearchGetFileContent (доступен с 6.5.6)

OnSearchGetFileContent
======================

Включить вкладки

Описание и параметры

Смотрите также

Пример функции-обработчика

### Описание и параметры

```
mixed
функция-обработчик(
	string absolute_path,
	string SEARCH_SESS_ID
);Копировать
```

Событие "OnSearchGetFileContent" вызывается во время переиндексации данных главного модуля [CSearch::ReIndexFile](/api_help/search/classes/csearch/reindexfile.php).

#### Параметры

| Параметр | Описание |
| --- | --- |
| absolute\_path | Абсолютный путь к индексируемому файлу. |
| SEARCH\_SESS\_ID | Идентификатор текущей сессии индексации. Может использоваться в обработчике события для добавления в поисковый индекс дополнительного контента с помощью метода [CSearch::Index](/api_help/search/classes/csearch/indexs.php). |

#### Возвращаемое значение

Функция-обработчик может вернуть массив описывающий содержимое файла. Массив должен иметь следующую структуру:

* **TITLE** - заголовок (обязательное поле);
* **CONTENT** - содержимое документа;
* **PROPERTIES** - массив свойств документа (обязательное). Если свойств нет, то должен быть передан пустой массив. Содержимое элемента этого массива с именем указанным в настройках модуля как "Код свойства страницы в котором хранятся теги" будет занесен в теги;

Или может вернуть false, если не знает как файл должен быть обработан.

### Смотрите также

* [CSearch::ReIndexFile](/api_help/search/classes/csearch/reindexfile.php)
* [Обработка событий](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Пример функции-обработчика

```
<?
//init.php
// индексируем сжатые gzip файлы.
// регистрируем обработчик события "OnSearchGetFileContent" модуля "search"
AddEventHandler("search", "OnSearchGetFileContent", array("CMyClass", "OnSearchGetFileContent_gzip"));
class CMyClass
{
	public static function OnSearchGetFileContent_gzip($absolute_path)
	{
		if(file_exists($absolute_path) && is_file($absolute_path) && substr($absolute_path, -3) == ".gz")
		{
			return array(
				"TITLE" => basename($absolute_path),
				"CONTENT" => implode("\n", gzfile($absolute_path)),
				"PROPERTIES" => array(),
			);
		}
		else
			return false;
	}
}
?>Копировать
```

Новинки документации в соцсетях: