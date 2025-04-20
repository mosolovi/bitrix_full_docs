[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

CCourseImport (доступен с 5.0.3)

CCourseImport
=============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CCourseImport::CCourseImport(
	string PACKAGE_DIR,
	array arSITE_ID
);Копировать
```

Конструктор класса CCourseImport. Инициализирует импортируемый курс.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| PACKAGE\_DIR | Путь к директории (относительно корня сайта) с архивом курса. |
| arSITE\_ID | Массив идентификаторов сайтов, к которым будет привязан импортируемый курс. |

**Примечание**

Если инициализация прошла неудачно, в свойстве LAST\_ERROR объекта будет
содержаться текст ошибки.

#### Смотрите также

* [CCourseImport](/api_help/learning/classes/ccourseimport/index.php)::[ImportPackage](/api_help/learning/classes/ccourseimport/importpackage.php)

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