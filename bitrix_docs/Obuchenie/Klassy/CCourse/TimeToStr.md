[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CCourse](/api_help/learning/classes/ccourse/index.php)

TimeToStr (доступен с 5.1.0)

TimeToStr
=========

```
string
CCourse::TimeToStr(
	int seconds
);Копировать
```

Возвращает количество дней, часов, минут и секунд в виде строки, содержащихся в *seconds*. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| seconds | Количество секунд. |

#### Возвращаемое значение

Метод возвращает строку вида "DDдн. HHч. MMмин. SSсек.".

#### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$seconds = 56789;
	$time = CCourse::TimeToStr($seconds);
	echo $time; //print 15 ч. 46 мин. 29 сек.
}
?>Копировать
```

Новинки документации в соцсетях: