[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CTestAttempt](/api_help/learning/classes/ctestattempt/index.php)

GetCount (доступен с 5.1.0)

GetCount
========

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
int
CTestAttempt::GetCount(
	int TEST_ID
	int STUDENT_ID
);Копировать
```

Возвращает количество попыток студента для указанного теста. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| TEST\_ID | Идентификатор теста. |
| STUDENT\_ID | Идентификатор студента. |

#### Возвращаемое значение

Число - количество попыток.

#### Смотрите также

- [CTestAttempt](/api_help/learning/classes/ctestattempt/index.php)::[GetList](/api_help/learning/classes/ctestattempt/getlist.php)

### Примеры использования

```
<?
if (CModule::IncludeModule("learning"))
{
	$TEST_ID = 33;
	$STUDENT_ID = 165;
	$cnt = CTestAttempt::GetCount($TEST_ID, $STUDENT_ID);
	echo "Number of attempts:".$cnt;
}
?>Копировать
```

Новинки документации в соцсетях: