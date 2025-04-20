[Информационные блоки](/api_help/iblock/index.php)

[События](/api_help/iblock/events/index.php)

OnBeforeIBlockElementAdd (доступно с 4.0.6)

OnBeforeIBlockElementAdd
========================

Включить вкладки

Описание и параметры

Примеры функции-обработчика

Смотрите также

### Описание и параметры

```
bool функция-обработчик(
	array &arParams 
);Копировать
```

Событие вызывается в методе [CIBlockElement::Add](/api_help/iblock/classes/ciblockelement/add.php) до вставки элемента информационного блока, и может быть использовано для отмены вставки или переопределения некоторых полей.

#### Параметры

| Параметр | Описание |
| --- | --- |
| **arParams** | [Массив полей](/api_help/iblock/fields.php#felement) нового элемента информационного блока. |

**Обратите внимание, что** все параметры данного обработчика являются ссылками на исходные переменные. Поэтому если вы измените значение параметра внутри обработчика, это приведет к смене значения исходной переменной поступившей на вход функции-обработчика.

#### Возвращаемое значение

Для отмены добавления и прекращении выполнения метода [CIBlockElement::Add](/api_help/iblock/classes/ciblockelement/add.php) необходимо в функции-обработчике создать исключение методом $APPLICATION->[ThrowException()](/api_help/main/reference/cmain/throwexception.php) и вернуть *false*.

### Примеры функции-обработчика

```
<?
// файл /bitrix/php_interface/init.php
// регистрируем обработчик
AddEventHandler("iblock", "OnBeforeIBlockElementAdd", Array("MyClass", "OnBeforeIBlockElementAddHandler"));
class MyClass
{
	// создаем обработчик события "OnBeforeIBlockElementAdd"
	public static function OnBeforeIBlockElementAddHandler(&$arFields)
	{
		if(strlen($arFields["CODE"])<=0)
		{
			global $APPLICATION;
			$APPLICATION->throwException("Введите символьный код.");
			return false;
		}
	}
}
?>Копировать
```

```
//пример обработчика, который при сохранении элемента переводит в транслит его заголовок, добавляет к заголовку текущую дату (для уникальности) и передает в поле "Символьный код"
// файл /bitrix/php_interface/init.php 
/ регистрируем обработчик
AddEventHandler("iblock", "OnBeforeIBlockElementAdd", Array("CymCode", "OnBeforeIBlockElementAddHandler")); 
class CymCode 
{ 
	// создаем обработчик события "OnBeforeIBlockElementAdd" 
	public static function OnBeforeIBlockElementAddHandler(&$arFields) 
	{ 
		if(strlen($arFields["CODE"])<=0) 
		{ 
			$arFields["CODE"] = CymCode::imTranslite($arFields["NAME"])."_".date('dmY'); 
				log_array($arFields); // убрать после отладки 
			return; 
		} 
	} 
	// записывает все что передадут в /bitrix/log.txt 
	function log_array() { 
		$arArgs = func_get_args(); 
		$sResult = ''; 
		foreach($arArgs as $arArg) { 
			$sResult .= "\n\n".print_r($arArg, true); 
		} 
		if(!defined('LOG_FILENAME')) { 
		define('LOG_FILENAME', $_SERVER['DOCUMENT_ROOT'].'/bitrix/log.txt'); 
		} 
		AddMessage2Log($sResult, 'log_array -> '); 
	} 
	function imTranslite($str){ 
	// транслитерация корректно работает на страницах с любой кодировкой 
	// ISO 9-95 
		static $tbl= array(
			'а'=>'a', 'б'=>'b', 'в'=>'v', 'г'=>'g', 'д'=>'d', 'е'=>'e', 'ж'=>'g', 'з'=>'z',
			'и'=>'i', 'й'=>'y', 'к'=>'k', 'л'=>'l', 'м'=>'m', 'н'=>'n', 'о'=>'o', 'п'=>'p',
			'р'=>'r', 'с'=>'s', 'т'=>'t', 'у'=>'u', 'ф'=>'f', 'ы'=>'y', 'э'=>'e', 'А'=>'A',
			'Б'=>'B', 'В'=>'V', 'Г'=>'G', 'Д'=>'D', 'Е'=>'E', 'Ж'=>'G', 'З'=>'Z', 'И'=>'I',
			'Й'=>'Y', 'К'=>'K', 'Л'=>'L', 'М'=>'M', 'Н'=>'N', 'О'=>'O', 'П'=>'P', 'Р'=>'R',
			'С'=>'S', 'Т'=>'T', 'У'=>'U', 'Ф'=>'F', 'Ы'=>'Y', 'Э'=>'E', 'ё'=>"yo", 'х'=>"h",
			'ц'=>"ts", 'ч'=>"ch", 'ш'=>"sh", 'щ'=>"shch", 'ъ'=>"", 'ь'=>"", 'ю'=>"yu", 'я'=>"ya",
			'Ё'=>"YO", 'Х'=>"H", 'Ц'=>"TS", 'Ч'=>"CH", 'Ш'=>"SH", 'Щ'=>"SHCH", 'Ъ'=>"", 'Ь'=>"",
			'Ю'=>"YU", 'Я'=>"YA", ' '=>"_", '№'=>"", '«'=>"<", '»'=>">", '—'=>"-" 
		); 
		return strtr($str, $tbl); 
	} 
}Копировать
```

```
//пропорциональное изменение размеров изображений, добавленных как пользовательское свойство: 
AddEventHandler("iblock", "OnBeforeIBlockElementAdd", Array("MyClass", "OnBeforeIBlockElementAddHandler"));
class MyClass
{
	public static function OnBeforeIBlockElementAddHandler(&$arFields)
	{
		foreach($arFields[PROPERTY_VALUES][28] as &$file):
			CAllFile::ResizeImage(
				$file, 
				array("width" => "200", "height" => "200"), 
				BX_RESIZE_IMAGE_PROPORTIONAL
			);
		endforeach;
	}
}Копировать
```

### Смотрите также

* [Событие "OnAfterIBlockElementAdd"](/api_help/iblock/events/onafteriblockelementadd.php)
* [CIBlockElement::Add](/api_help/iblock/classes/ciblockelement/add.php)
* [Обработка событий](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

Новинки документации в соцсетях: