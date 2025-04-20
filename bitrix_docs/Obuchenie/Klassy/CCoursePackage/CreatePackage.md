[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CCoursePackage](/api_help/learning/classes/ccoursepackage/index.php)

CreatePackage (доступен с 5.0.3)

CreatePackage
=============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CCoursePackage::CreatePackage(
	int PACKAGE_DIR
);Копировать
```

Создает архив с учебным курсом. Метод нестатический.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| PACKAGE\_DIR | Путь (относительно корня сайта) к директории, куда будет скопирован архив курса. | 5.1.2 |

#### Возвращаемое значение

Метод возвращает *true*, если создание архива прошло успешно. При
возникновении ошибки метод вернет false, а в свойстве объекта LAST\_ERROR будет
содержаться текст ошибки.

#### Смотрите также

* [CCoursePackage](/api_help/learning/classes/ccoursepackage/index.php)::[CCoursePackage](/api_help/learning/classes/ccoursepackage/ccoursepackage.php)
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