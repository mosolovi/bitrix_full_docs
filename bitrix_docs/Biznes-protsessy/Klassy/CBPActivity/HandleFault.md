[Бизнес-процессы](/api_help/bizproc/index.php)

[Классы](/api_help/bizproc/bizproc_classes/index.php)

[CBPActivity](/api_help/bizproc/bizproc_classes/CBPActivity/index.php)

HandleFault

HandleFault
===========

```
void
public function HandleFault(
	Exception exception
);Копировать
```

Этот метод вызывается исполняющей средой при возникновении ошибки выполнения действия. Метод может быть переопределен, если при возникновении ошибки выполнения действия необходимо выполнить какой-либо код. По умолчанию метод ничего не делает и может быть переопределен в классе-наследнике.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *exception* | Объект типа Exception, представляющий собой ошибку выполнения |

#### Примеры использования

```
<?
public function HandleFault(Exception $exception)
{
	if ($exception == null)
		throw new Exception("exception");
	$status = $this->Cancel();
	if ($status == CBPActivityExecutionStatus::Canceling)
		return CBPActivityExecutionStatus::Faulting;
	return $status;
}
?>Копировать
```

Новинки документации в соцсетях: