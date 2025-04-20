[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CLesson](/api_help/learning/classes/clesson/index.php)

GetByID (доступен с 5.1.0, устарел и удален с 12.0.0)

GetByID
=======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
CDBResult
CLesson::GetByID(
	int ID
);Копировать
```

Возвращает урок по его коду ID. Учитываются права доступа текущего пользователя.

**Примечание:** начиная с версии 12.0.0, метод считается устаревшим. Вместо него для работы с главами/уроками следует использовать класс **CLearnLesson**.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор урока. |

#### Возвращаемое значение

Возвращается объект [CDBResult](/api_help/main/reference/cdbresult/index.php).

### Смотрите также

- [CDBResult](/api_help/main/reference/cdbresult/index.php)
- [Поля урока](/api_help/learning/fields.php#lesson)
- [CLesson](/api_help/learning/classes/clesson/index.php)::[GetList](/api_help/learning/classes/clesson/getlist.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$LESSON_ID = 651;
    
	$res = CLesson::GetByID($LESSON_ID);
	if ($arLesson = $res->GetNext())
	{
		echo "Name: ".$arLesson["NAME"];
	}
}
?>Копировать
```

Новинки документации в соцсетях: