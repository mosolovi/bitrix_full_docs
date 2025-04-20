[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

CCoursePackage (доступен с 5.0.3)

CCoursePackage
==============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CCoursePackage::CCoursePackage(
	int COURSE_ID
);Копировать
```

Конструктор класса CCoursePackage инициализирует экспортируемый курс. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| COURSE\_ID | Идентификатор курса. |

**Примечание**

Если инициализация прошла неудачно, в свойстве LAST\_ERROR объекта будет содержаться текст ошибки.

#### Смотрите также

* [CCoursePackage](/api_help/learning/classes/ccoursepackage/index.php)::[CreatePackage](/api_help/learning/classes/ccoursepackage/createpackage.php)
* [CCoursePackage](/api_help/learning/classes/ccoursepackage/index.php)::[CreateManifest](/api_help/learning/classes/ccoursepackage/createmanifest.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$COURSE_ID = 97;
	if (CCourse::GetPermission($COURSE_ID) >= 'W')
	{
		@set_time_limit(0);
		$package = new CCoursePackage($COURSE_ID);
		if (strlen($package->LAST_ERROR) > 0)
		{
			echo "Error: ".$package->LAST_ERROR;
		}
		else
		{
			$success = $package->CreatePackage($PACKAGE_DIR = "/upload/mypackage/");
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