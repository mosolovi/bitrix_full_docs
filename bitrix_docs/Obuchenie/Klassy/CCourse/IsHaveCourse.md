[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CCourse](/api_help/learning/classes/ccourse/index.php)

IsHaveCourse (доступен с 5.0.3, удален с 8.0.0)

IsHaveCourse
============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CCourse::IsHaveCourse(
	string MIN_PERMISSION = "W"
);Копировать
```

Определяет, имеет ли текущий пользователь минимальное право доступа
*MIN\_PERMISSION* хотя бы к одному курсу.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| MIN\_PERMISSION | Минимальное право доступа. По умолчанию "W" - запись. |

#### Возвращаемое значение

Метод возвращает *true*, если пользователь имеет доступ хотя бы к одному
курсу, в противном случае - *false*.

#### Смотрите также

- [CCourse](/api_help/learning/classes/ccourse/index.php)::[GetList](/api_help/learning/classes/ccourse/getlist.php)

### Примеры использования

```
<?
if (CCourse::IsHaveCourse($MIN_PERMISSION = "W"))
{
	echo "You are a teacher!";
}
else
{
	echo "Access denied!";
}
?>Копировать
```

Новинки документации в соцсетях: