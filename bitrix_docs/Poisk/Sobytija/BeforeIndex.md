[Поиск](/api_help/search/index.php)

[События](/api_help/search/events/index.php)

BeforeIndex (доступен с 5.1.0)

BeforeIndex
===========

Включить вкладки

Описание и параметры

Смотрите также

Примеры

### Описание и параметры

```
функция-обработчик(
	array arFields
);Копировать
```

Событие "BeforeIndex" вызывается перед индексацией элемента методом [CSearch::Index](/api_help/search/classes/csearch/indexs.php).

  

Важно! Функция-обработчик не принимает параметр arFields по ссылке. Не верно: `function BeforeIndexHandler(&$arFields)`. Верно: `function BeforeIndexHandler($arFields)`.

#### Параметры

| Параметр | Описание |
| --- | --- |
| arFields | Массив следующего содержания:  * **MODULE\_ID** - идентификатор модуля (не изменится); * **ITEM\_ID** - идентификатор элемента (не изменится); * **PARAM1** - первый параметр элемента; * **PARAM2** - второй параметр элемента; * **DATE\_FROM** - дата начала активности элемента; * **DATE\_TO** - дата окончания активности элемента; * **TITLE** - заголовок; * **BODY** - содержание; * **TAGS** - теги элемента; * **SITE\_ID** - массив сайтов; * **PERMISSIONS** - массив идентификаторов групп пользователей которым разрешено чтение; * **URL** - адрес относительно корня сайта, по которому доступен данный элемент; |

Данный обработчик может модифицировать поля параметра arFields и должен вернуть его как результат своей работы.

**Важные моменты**

* Если в обработчике проводятся модификации поля *SITE\_ID*, то надо помнить,что индексы в массиве должны быть с нуля и по порядку. Иначе массив будет воспринят как ассоциативный и элементы привяжутся к сайтам неверно (вместо *SITE\_ID* окажутся числа и элементы пропадут из поиска).
* Чтобы не добавлять запись в индекс (например, если надо какой-то подраздел инфоблока не индексировать), необходимо в функции-обработчике выполнить:  

  ```
  unset($arFields["BODY"]);
  unset($arFields["TITLE"]);Копировать
  ```
* Если выполняются проверки типа:  

  ```
  $bTitle = array_key_exists("TITLE", $arFields);
  $bBody = array_key_exists("BODY", $arFields);
  if($bTitle && $bBody && strlen($arFields["BODY"])<=0 && strlen($arFields["TITLE"])<=0)Копировать
  ```

  то для исключения элемента из индекса как записи следует выполнять:  

  ```
  $arFields["BODY"]='';
  $arFields["TITLE"]='';Копировать
  ```

### Смотрите также

* [CSearch::Index](/api_help/search/classes/csearch/indexs.php)

### Примеры

#### Пример функции-обработчика:

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler("search", "BeforeIndex", Array("MyClass", "BeforeIndexHandler"));
class MyClass
{
	// создаем обработчик события "BeforeIndex"
	public static function BeforeIndexHandler($arFields)
	{
		if($arFields["MODULE_ID"] == "iblock" && $arFields["PARAM2"] == 33)
		{
			if(array_key_exists("BODY", $arFields))
			{
				$arFields["BODY"] .= " самые свежие новости";
			}
		}
		return $arFields;
	}
}
?>Копировать
```

#### Пример использования функции-обработчика:

Пример использования функции-обработчика, чтобы компонент [search.title](http://dev.1c-bitrix.ru/user_help/settings/search/components_2/search_title.php) проводил поиск не только по заголовкам, но и некоторому свойству:

```
// регистрируем обработчик
AddEventHandler("search", "BeforeIndex", "BeforeIndexHandler");
 // создаем обработчик события "BeforeIndex"
function BeforeIndexHandler($arFields)
{
	if(!CModule::IncludeModule("iblock")) // подключаем модуль
		return $arFields;
	if($arFields["MODULE_ID"] == "iblock")
	{
		$db_props = CIBlockElement::GetProperty(                        // Запросим свойства индексируемого элемента
			$arFields["PARAM2"],         // BLOCK_ID индексируемого свойства
			$arFields["ITEM_ID"],          // ID индексируемого свойства
			array("sort" => "asc"),       // Сортировка (можно упустить)
			Array("CODE"=>"CML2_ARTICLE")); // CODE свойства (в данном случае артикул)
		if($ar_props = $db_props->Fetch())
			$arFields["TITLE"] .= " ".$ar_props["VALUE"];   // Добавим свойство в конец заголовка индексируемого элемента
	}
	return $arFields; // вернём изменения
}Копировать
```

Новинки документации в соцсетях: