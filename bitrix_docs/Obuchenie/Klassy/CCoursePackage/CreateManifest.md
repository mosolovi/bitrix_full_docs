[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CCoursePackage](/api_help/learning/classes/ccoursepackage/index.php)

CreateManifest (доступен с 5.0.3)

CreateManifest
==============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
string
CCoursePackage::CreateManifest();Копировать
```

Возвращает манифест (в xml-формате) архива учебного курса. Метод нестатический.

#### Параметры метода

Нет параметров.

#### Возвращаемое значение

Метод возвращает строку - содержимое файла imsmanifest.xml архива учебного курса.

#### Смотрите также

* [CCoursePackage](/api_help/learning/classes/ccoursepackage/index.php)::[CCoursePackage](/api_help/learning/classes/ccoursepackage/ccoursepackage.php)
* [CCoursePackage](/api_help/learning/classes/ccoursepackage/index.php)::[CreatePackage](/api_help/learning/classes/ccoursepackage/createpackage.php)

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
			echo htmlspecialchars($package->CreateManifest());
		}
	}
}
?>Копировать
```

Новинки документации в соцсетях: