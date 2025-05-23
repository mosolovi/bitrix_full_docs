[Подписка, рассылки](/api_help/subscribe/index.php)

[Классы](/api_help/subscribe/classes/index.php)

[CPostingGeneral](/api_help/subscribe/classes/cpostinggeneral/index.php)

SendMessage (доступен с 3.1.1)

SendMessage
===========

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
mixed
CPosting::SendMessage(
	int ID,
	int timeout = 0,
	int maxcount = 0,<
	bool check_charset = false,
);Копировать
```

Нестатический метод отправляет выпуск в почтовую рассылку по адресам, указанным в таблице **b\_posting\_email** с соответствующим идентификатором выпуска. При этом обновляя статусы:

* Y - еще не отправлялось
* N - отправлено
* Е - с ошибками

Выпуски со статусом "Успешно отправлен" повторно не отправляются. Если у выпуска установлен статус "Частично отправлен", то выпуск отправляется по оставшимся адресам.

Сначала выполняется попытка получения блокировки выпуска (см. [CPosting::Lock](/api_help/subscribe/classes/cposting/cpostinglock.php)). Если блокировку получить не удалось, то отправка считается частичной и возвращается "CONTINUE". Затем формируется тело письма для отправки и в цикле по адресам подписчиков осуществляется отправка выпуска с использованием функции [bxmail](/api_help/main/functions/other/bxmail.php).

В режиме отправки "Персонально каждому получателю" перед вызовом [bxmail](/api_help/main/functions/other/bxmail.php) вызываются обработчики события BeforePostingSendMail.

В цикле отправки в очереди адресов делаются отметки об успешной отправке или ошибке.

С выпуска снимается блокировка(см. [CPosting::UnLock](/api_help/subscribe/classes/cposting/cpostingunlock.php)).

#### Параметры

| Параметр | Описание | C версии |
| --- | --- | --- |
| ID | Идентификатор выпуска. |  |
| timeout | Максимальное время отправки в секундах. При превышении этого времени прерывается работа и устанавливается статус выпуска "Частично отправлен". Параметр имеет значение только при методе отправки "Персонально каждому получателю". Если timeout=0, то отправка производится за один шаг. | 3.2.0 |
| maxcount | Максимальное количество писем для отправки. При превышении этого количества прерывается работа и устанавливается статус выпуска "Частично отправлен". Параметр имеет значение только при методе отправки "Персонально каждому получателю". Если maxcount=0, то отправка производится за один шаг. | 4.0.5 |
| check\_charset | Сопоставлять текущую кодировку (константа LANG\_CHARSET) с кодировкой в которой составлен выпуск или нет. Если кодировки не совпадают, то вернется "CONTINUE". Используется при отправке выпусков с помощью агентов. Сравнение выполняется без учета регистра кодировок. | 8.0.1 |

#### Возвращаемые значения

Функция возвращает true при успешной отправке, false при неуспешной, "CONTINUE" при частичной отправке. При неуспешной отправке переменная LAST\_ERROR класса содержит сообщение об ошибке.

### Смотрите также

- [bxmail](/api_help/main/functions/other/bxmail.php)

### Примеры использования

```
<?
if($action=="send" && $ID>0):
	if(($res = $cPosting->SendMessage($ID, COption::GetOptionString("subscribe", "posting_interval"))) !== false):
		if($res === "CONTINUE"):
?>
<script language="JavaScript" type="text/javascript">
<!--
function DoNext(){window.location="<?echo $APPLICATION->GetCurPage()."?ID=".$ID."&action=send&lang=".LANG."&rnd=".rand();?>";}
setTimeout('DoNext()', 2500);
//-->
</script>
<?
		else:
			$strOk = "Sent successfully.";
		endif; //$res === "CONTINUE"
	endif; //$cPosting->SendMessage
	$strError .= $cPosting->LAST_ERROR;
endif; //$action=="send"Копировать
```

Новинки документации в соцсетях: