[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CTest](/api_help/learning/classes/ctest/index.php)

GetCount (доступен с 5.1.1)

GetCount
========

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
int
CTest::GetCount(
	array arFilter = Array()
);Копировать
```

Возвращает количество тестов по заданному фильтру. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arFilter | Массив вида  *array("фильтруемое поле"=>"значение фильтра" [, ...])*. Описание фильтра см. в [CTest::GetList](/api_help/learning/classes/ctest/getlist.php).  По умолчанию тесты не фильтруются. |

#### Возвращаемое значение

Число - количество тестов.

#### Смотрите также

* [CTest](/api_help/learning/classes/ctest/index.php)::[GetList](/api_help/learning/classes/ctest/getlist.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$COURSE_ID = 97;
    
	$cnt = CTest::GetCount(Array("ACTIVE" => "Y", "COURSE_ID" => $COURSE_ID));
	echo "Number of tests: ".$cnt;
}
?>Копировать
```

```
<?
if (CModule::IncludeModule("learning"))
{
	$COURSE_ID = 97;
    
	$cnt = CTest::GetCount(Array("CHECK_PERMISSIONS" => "N", "COURSE_ID" => $COURSE_ID));
	echo "Number of tests: ".$cnt;
}
?>Копировать
```

Новинки документации в соцсетях: