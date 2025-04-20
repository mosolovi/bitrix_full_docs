[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CStudent](/api_help/learning/classes/cstudent/index.php)

GenerateTranscipt (доступен с 5.1.0)

GenerateTranscipt
=================

```
int
CStudent::GenerateTranscipt(
	int TranscriptLength = 8
);Копировать
```

Возвращает случайный числовой идентификатор. Метод нестатический.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| TranscriptLength | Длина числового идентификатора. По умолчанию равна 8. | 5.1.2 |

#### Возвращаемое значение

Случайное число.

#### Смотрите также

* [CStudent](/api_help/learning/classes/cstudent/index.php)::[Add](/api_help/learning/classes/cstudent/add.php)

#### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	echo CStudent::GenerateTranscipt();
}
?>Копировать
```

Новинки документации в соцсетях: