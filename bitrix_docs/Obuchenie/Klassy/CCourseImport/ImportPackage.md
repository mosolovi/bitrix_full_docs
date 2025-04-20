[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CCourseImport](/api_help/learning/classes/ccourseimport/index.php)

ImportPackage (доступен с 5.0.3)

ImportPackage
=============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CCourseImport::ImportPackage();Копировать
```

Метод импортирует курс. Метод нестатический.

#### Параметры метода

Нет параметров.

#### Возвращаемое значение

Метод возвращает *true*, если создание курса прошло успешно. При
возникновении ошибки метод вернёт *false*, а в свойстве объекта LAST\_ERROR
будет содержаться текст ошибки.

#### Смотрите также

* [CCourseImport](/api_help/learning/classes/ccourseimport/index.php)::[CCourseImport](/api_help/learning/classes/ccourseimport/ccourseimport.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	if ($USER->IsAdmin())
	{
		@set_time_limit(0);
		$package = new CCourseImport($PACKAGE_DIR = "/upload/mypackage/", Array("ru", "en"));
		if (strlen($package->LAST_ERROR) > 0)
		{
			echo "Error: ".$package->LAST_ERROR;
		}
		else
		{
			$success = $package->ImportPackage();
			if (!$success)
				echo "Error: ".$package->LAST_ERROR;
			else
				echo "Ok!";
		}
	}
}
?>Копировать
```

Новинки документации в соцсетях: