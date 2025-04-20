[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnAfterLanguageAdd (с версии 25.0.0)

OnAfterLanguageAdd
==================

Включить вкладки

Описание и параметры

Пример использования

### Описание и параметры

```
функция-обработчик(
	array fields
);Копировать
```

Событие "OnAfterLanguageAdd" вызывается в CAllLanguage::Add после добавления записи в базу данных.

#### Параметры

| Параметр | Описание |
| --- | --- |
| *fields* | Массив полей добавленного языка. Массив вида `array("поле"=>"значение" [, ...])`. |

### Пример использования

```
$eventManager = Main\EventManager::getInstance();
$eventManager->registerEventHandlerCompatible(
	'main',
	'OnAfterLanguageAdd',
	'mymodule',
	'MyClass',
	'MyMethod'
);
class MyClass
{
	public static function MyMethod($param)
	{
		$langId = $param['LID'];
		// ....
	}
}Копировать
```

#### Смотрите также

* [CLanguage::Add](/api_help/main/reference/clanguage/add.php)
* [Событие "OnBeforeLanguageDelete"](/api_help/main/events/onbeforelanguagedelete.php)
* [Событие "OnLanguageDelete"](/api_help/main/events/onlanguagedelete.php)

Новинки документации в соцсетях: