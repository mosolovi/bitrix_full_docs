[Веб-формы](/api_help/form/index.php)

Создание собственных валидаторов полей веб-форм

Создание собственных валидаторов полей веб-форм
===============================================

Включить вкладки

Структура валидатора

Интеграция валидатора

Пример

Смотрите также

### Структура валидатора

Валидатор представляет собой класс или набор функций следующей структуры:

| Метод | Описание |
| --- | --- |
| Описание валидатора | Функция, передающая обработчику валидаторов описание валидатора, названия методов и пр. |
| Настройки валидатора | Функция, возвращающая массив настроек валидатора. |
| Обработка настроек | Набор функций, отвечающий за подготовку настроек к занесению в БД и обратное преобразование. |
| Функция валидации | Собственно, валидатор. |

Поскольку работать с набором отдельных функций неудобно, рекомендуется
объединить их в класс (пространство имен). Исходя из этой рекомендации будет
идти дальнейшее описание, а также, реализован приводимый пример. В примере
валидатор "Число в промежутке" реализован в виде класса
`CFormCustomValidatorNumberEx`.

**Описание валидатора**

Описание валидатора представляет собой метод, возвращающий ассоциативный
массив следующей структуры:

| Параметр | Описание |
| --- | --- |
| **NAME** | Уникальный строковой идентифкатор валидатора. |
| **DESCRIPTION** | Название валидатора. |
| **TYPES** | Массив типов полей, к которым применим валидатор. |
| **SETTINGS** | Название метода, возвращающего массив настроек валидатора. Не обязателен. В случае реализации валидатора в виде класса, значение представляет собой массив ("имя\_класса", "имя\_метода"). |
| **CONVERT\_TO\_DB** | Название метода, отвечающего за проверку параметров валидатора и преобразование массива настроек в строку для сохранения. Не обязателен, если валидатор не имеет настроек. В случае реализации валидатора в виде класса, значение представляет собой массив ("имя\_класса", "имя\_метода"). |
| **CONVERT\_FROM\_DB** | Название метода, отвечающего за обратное преобразование строки параметров валидатора в массив. Не обязателен, если валидатор не имеет настроек. В случае реализации валидатора в виде класса, значение представляет собой массив ("имя\_класса", "имя\_метода"). |
| **HANDLER** | Название основного метода, отвечающего собственно за валидацию значения поля. В случае реализации валидатора в виде класса, значение представляет собой массив ("имя\_класса", "имя\_метода"). |

Пример:

```
 function GetDescription()
{
	return array(
		"NAME"            => "custom_number_ex",                                   // идентификатор
		"DESCRIPTION"     => "Число в промежутке",                                 // наименование
		"TYPES"           => array("text", "textarea"),                            // типы полей
		"SETTINGS"        => array("CFormCustomValidatorNumberEx", "GetSettings"), // метод, возвращающий массив настроек
		"CONVERT_TO_DB"   => array("CFormCustomValidatorNumberEx", "ToDB"),        // метод, конвертирующий массив настроек в строку
		"CONVERT_FROM_DB" => array("CFormCustomValidatorNumberEx", "FromDB"),      // метод, конвертирующий строку настроек в массив
		"HANDLER"         => array("CFormCustomValidatorNumberEx", "DoValidate")   // валидатор
	);
}Копировать
```

**Параметры валидатора**

Метод, заданный элементом `SETTINGS`, должен возвращать массив
элементов вида:

```
"имя_параметра" => array(
	"TITLE"   => "название_параметра",
	"TYPE"    => "тип_параметра",
	"DEFAULT" => "значение_по_умолчанию",
	"VALUES"  => array(
		"значение1" => "наименование_значения1",
		"значение2" => "наименование_значения2",
		"значение3" => "наименование_значения3"
	)
)Копировать
```

| Параметр | Описание |
| --- | --- |
| *имя\_параметра* | Ключом массива является уникальное в рамках данного валидатора строковое наименование параметра. |
| **TITLE** | Наименование параметра |
| **TYPE** | Тип поля для ввода значения параметра. Может принимать следющие значения:  * **TEXT** - обычное текстовое поле; * **CHECKBOX** - галочка. Результатом будет значение   `{Y|N}`; * **DROPDOWN** - выпадающий список; * **DATE** - поле для ввода даты. |
| **DEFAULT** | Значение параметра по умолчанию. |
| **VALUES** | Массив элементов вида "*значение*" => "*наименование значения*" для параметров типа `DROPDOWN` |

Пример:

```
 function GetSettings()
{
	return array(
		"NUMBER_FROM" => array(
			"TITLE"   => "Нижний порог числа",
			"TYPE"    => "TEXT",
			"DEFAULT" => "0",
		),
    
		"NUMBER_TO" => array(
			"TITLE"   => "Верхний порог числа",
			"TYPE"    => "TEXT",
			"DEFAULT" => "100",
		),
    
		"NUMBER_FLOAT" => array(
			"TITLE"   => "Не только целое",
			"TYPE"    => "CHECKBOX",
			"DEFAULT" => "Y",
		),
	);
}Копировать
```

**Обработка параметров**

Обработка параметров валидатора требует двух методов, задаваемых в описании
параметрами `CONVERT_TO_DB` и `CONVERT_FROM_DB`. Первый из
них получает на вход массив значений параметров и должен вернуть их строковое
представление. Второй - совершить обратное преобразование. Оба метода могут
также совершать произвольные манипуляции со значениями параметров.

Пример:

```
 function ToDB($arParams)
{
	// проверка переданных параметров
	$arParams["NUMBER_FLOAT"] = $arParams["NUMBER_FLOAT"] == "Y" ? "Y" : "N";
	$arParams["NUMBER_FROM"]  = $arParams["NUMBER_FLOAT"] == "Y" ? floatval($arParams["NUMBER_FROM"]) : intval($arParams["NUMBER_FROM"]);
	$arParams["NUMBER_TO"]    = $arParams["NUMBER_FLOAT"] == "Y" ? floatval($arParams["NUMBER_TO"]) : intval($arParams["NUMBER_TO"]);
  
	// перестановка значений порогов, если требуется
	if ($arParams["NUMBER_FROM"] > $arParams["NUMBER_TO"])
	{
		$tmp                     = $arParams["NUMBER_FROM"];
		$arParams["NUMBER_FROM"] = $arParams["NUMBER_TO"];
		$arParams["NUMBER_TO"]   = $tmp;
	}
  
	// возвращаем сериализованную строку
	return serialize($arParams);
}
function FromDB($strParams)
{
	// никаких преобразований не требуется, просто вернем десериализованный массив
	return unserialize($strParams);
}Копировать
```

**Валидатор**

Основной метод получает на вход 4 параметра: массив параметров валидатора,
массив параметров вопроса, массив ответов вопроса и массив значений ответов. Он
должен вернуть `true` в случае успешной валидации значения и
`false` в случае ошибки. Текст ошибки возвращается посредством
`CMain::ThrowException()`. В тексте ошибки можно использовать шаблон
`#FIELD_NAME#` для получения названия поля, в котором произошла
ошибка.

Пример:

```
 function DoValidate($arParams, $arQuestion, $arAnswers, $arValues)
{
	global $APPLICATION;
  
	foreach ($arValues as $value)
	{
		// пустые значения пропускаем
		if (strlen($value) <= 0) continue;
    
		// приведем значение к числу
		$value = $arParams["NUMBER_FLOAT"] == "Y" ? floatval($value) : intval($value);
    
		// проверим нижний порог числа
		if (strlen($arParams["NUMBER_FROM"]) > 0 && $value < intval($arParams["NUMBER_FROM"]))
		{
			// вернем ошибку
			$APPLICATION->ThrowException("#FIELD_NAME#: слишком маленькое значение");
			return false;
		}
    
		// проверим верхний порог числа
		if (strlen($arParams["NUMBER_TO"]) > 0 && $value > intval($arParams["NUMBER_TO"]))
		{
			// вернем ошибку
			$APPLICATION->ThrowException("#FIELD_NAME#: слишком большое значение");
			return false;
		}
	}
  
	// все значения прошли валидацию, вернем true
	return true;
}Копировать
```

**Обратите внимание:** при обработке значений полей перечислимых типов
(dropdown, multiselect, radio, checkbox) валидатор получит на вход массив ID
выбранных ответов.

### Интеграция валидатора

Класс валидатора должен подключаться в любом месте, в котором он будет
доступен из административной панели и в публичной части (подробнее см. [порядок
выполнения страниц](/api_help/main/general/pageplan.php)), например, в **/bitrix/php\_interface/init.php**.
Непосредственно, файл валидатора может находиться где угодно, например, в
/bitrix/php\_interface/include/form/validators/. Подключение валидатора
производится установкой описательной функции валидатора в качестве обработчика
события `onFormValidatorBuildList`.

### Пример

Подытожив все вышесказанное, сформируем валидатор. Класс валидатора
расположим в файле
/bitrix/php\_interface/include/form/validators/val\_num\_ex.php

```
 <?
// Листинг файла /bitrix/php_interface/include/form/validators/val_num_ex.php
class CFormCustomValidatorNumberEx
{
	function GetDescription()
	{
		return array(
			"NAME"            => "custom_number_ex",                                   // идентификатор
			"DESCRIPTION"     => "Число в промежутке",                                 // наименование
			"TYPES"           => array("text", "textarea"),                            // типы полей
			"SETTINGS"        => array("CFormCustomValidatorNumberEx", "GetSettings"), // метод, возвращающий массив настроек
			"CONVERT_TO_DB"   => array("CFormCustomValidatorNumberEx", "ToDB"),        // метод, конвертирующий массив настроек в строку
			"CONVERT_FROM_DB" => array("CFormCustomValidatorNumberEx", "FromDB"),      // метод, конвертирующий строку настроек в массив
			"HANDLER"         => array("CFormCustomValidatorNumberEx", "DoValidate")   // валидатор
		);
	}
	function GetSettings()
	{
		return array(
			"NUMBER_FROM" => array(
				"TITLE"   => "Нижний порог числа",
				"TYPE"    => "TEXT",
				"DEFAULT" => "0",
			),
			"NUMBER_TO" => array(
				"TITLE"   => "Верхний порог числа",
				"TYPE"    => "TEXT",
				"DEFAULT" => "100",
			),
      
			"NUMBER_FLOAT" => array(
				"TITLE"   => "Не только целое",
				"TYPE"    => "CHECKBOX",
				"DEFAULT" => "Y",
			),
		);
	}
	function ToDB($arParams)
	{
		// проверка переданных параметров
		$arParams["NUMBER_FLOAT"] = $arParams["NUMBER_FLOAT"] == "Y" ? "Y" : "N";
		$arParams["NUMBER_FROM"]  = $arParams["NUMBER_FLOAT"] == "Y" ? floatval($arParams["NUMBER_FROM"]) : intval($arParams["NUMBER_FROM"]);
		$arParams["NUMBER_TO"]    = $arParams["NUMBER_FLOAT"] == "Y" ? floatval($arParams["NUMBER_TO"]) : intval($arParams["NUMBER_TO"]);
    
		// перестановка значений порогов, если требуется
		if ($arParams["NUMBER_FROM"] > $arParams["NUMBER_TO"])
		{
			$tmp                     = $arParams["NUMBER_FROM"];
			$arParams["NUMBER_FROM"] = $arParams["NUMBER_TO"];
			$arParams["NUMBER_TO"]   = $tmp;
		}
    
		// возвращаем сериализованную строку
		return serialize($arParams);
	}
	function FromDB($strParams)
	{
		// никаких преобразований не требуется, просто вернем десериализованный массив
		return unserialize($strParams);
	}
	
	function DoValidate($arParams, $arQuestion, $arAnswers, $arValues)
	{
		global $APPLICATION;
    
		foreach ($arValues as $value)
		{
			// пустые значения пропускаем
			if (strlen($value) <= 0) continue;
      
			// приведем значение к числу
			$value = $arParams["NUMBER_FLOAT"] == "Y" ? floatval($value) : intval($value);
      
			// проверим нижний порог числа
			if (strlen($arParams["NUMBER_FROM"]) > 0 && $value < intval($arParams["NUMBER_FROM"]))
			{
				// вернем ошибку
				$APPLICATION->ThrowException("#FIELD_NAME#: слишком маленькое значение");
				return false;
			}
      
			// проверим верхний порог числа
			if (strlen($arParams["NUMBER_TO"]) > 0 && $value > intval($arParams["NUMBER_TO"]))
			{
				// вернем ошибку
				$APPLICATION->ThrowException("#FIELD_NAME#: слишком большое значение");
				return false;
			}
		}
    
		// все значения прошли валидацию, вернем true
		return true;
	}
}
// установим метод CFormCustomValidatorNumberEx в качестве обработчика события
AddEventHandler("form", "onFormValidatorBuildList", array("CFormCustomValidatorNumberEx", "GetDescription"));
?>Копировать
```

После этого остается только вставить в /bitrix/php\_interface/init.php
строку

```
include_once($_SERVER["DOCUMENT_ROOT"]."/bitrix/php_interface/include/form/validators/val_num_ex.php");
Копировать
```

### Смотрите также

- [Класс CFormValidator](/api_help/form/classes/cformvalidator/index.php)
- [AddEventHandler](/api_help/main/functions/module/addeventhandler.php)

Новинки документации в соцсетях: