[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CTestResult](/api_help/learning/classes/ctestresult/index.php)

GetCount (доступен с 5.1.0)

GetCount
========

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
int
CTestResult::GetCount(
	int ATTEMPT_ID
);Копировать
```

Возвращает количество вопросов плана тестирования для указанной попытки. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ATTEMPT\_ID | Идентификатор попытки. |

#### Возвращаемое значение

Число - количество вопросов плана тестирования.

#### Смотрите также

* [CTestResult](index.php)::[GetList](getlist.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$ATTEMPT_ID = 588;
	$cnt = CTestResult::GetCount($ATTEMPT_ID);
	echo "Number of questions:".$cnt;
}
?>Копировать
```

Новинки документации в соцсетях: