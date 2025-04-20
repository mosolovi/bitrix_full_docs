[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CTestResult](/api_help/learning/classes/ctestresult/index.php)

GetProgress (доступен с 5.1.0)

GetProgress
===========

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
array
CTestResult::GetProgress(
	int ATTEMPT_ID
);Копировать
```

Возвращает количество отвеченных и неотвеченных вопросов плана
тестирования. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ATTEMPT\_ID | Идентификатор попытки. |

#### Возвращаемое значение

Метод возвращает ассоциативный массив с ключами:

* **DONE** - количество отвеченных вопросов теста.
* **TODO** - количество неотвеченных вопросов теста.

#### Смотрите также

* [CTestResult](index.php)::[GetList](getlist.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$ATTEMPT_ID = 588;
	$arStat = CTestResult::GetProgress($ATTEMPT_ID);
	echo $arStat["TODO"];
	echo $arStat["DONE"];
}
?>Копировать
```

Новинки документации в соцсетях: