[Задачи](/api_help/tasks/index.php)

[Классы](/api_help/tasks/classes/index.php)

[CTasks](/api_help/tasks/classes/ctasks/index.php)

GetList (10.0.2 - 12.0.9)

GetList
=======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
CDBResult
CTasks::GetList(
	array arOrder = array(),
	array arFilter = array(),
	array arSelect = array(),
	array arParams = array()
);Копировать
```

Возвращает список задач по фильтру **arFilter**, отсортированный в порядке **arOrder**.

**Примечание:** Метод принимает массив конфигурационных параметров и генерирует скрипты, необходимые для показа файлового диалога. Метод статический.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| *arOrder* | Массив для сортировки результата. Массив вида *array("поле сортировки"=>"направление сортировки" [, ...])*.   Поле для сортировки может принимать значения:  * **TITLE** - название задачи; * **DATE\_START** - дата старта; * **DEADLINE** - крайний срок; * **STATUS** - статус; * **PRIORITY** - приоритет; * **MARK** - оценка; * **CREATED\_BY** - постановщик; * **RESPONSIBLE\_ID** - исполнитель; * **GROUP\_ID** - рабочая группа.  Направление сортировки может принимать значения:  * **asc** - по возрастанию; * **desc** - по убыванию;    Необязательный. По умолчанию фильтруется по убыванию идентификатора задачи.   **Примечание**. Допускается сортировка по пользовательским полям. |  |
| *arFilter* | Массив вида  *array("фильтруемое поле"=>"значение фильтра" [, ...])*. Фильтруемое поле может принимать значения:  * **ID** - идентификатор задачи; * **PARENT\_ID** - идентификатор родительской задачи; * **GROUP\_ID** - идентификатор рабочей группы; * **CREATED\_BY** - постановщик; * **STATUS\_CHANGED\_BY** - пользователь, последним изменивший статус задачи; * **PRIORITY** - приоритет; * **FORUM\_TOPIC\_ID** - идентификатор темы форума; * **RESPONSIBLE\_ID** - исполнитель; * **TITLE** - название задачи (можно искать по шаблону [%\_]) ; * **TAG** -  тэг; * **REAL\_STATUS** - статус задачи. Константы отражающие статусы задач:   + CTasks::STATE\_NEW = 1;   + CTasks::STATE\_PENDING = 2;   + CTasks::STATE\_IN\_PROGRESS = 3;   + CTasks::STATE\_SUPPOSEDLY\_COMPLETED = 4;   + CTasks::STATE\_COMPLETED = 5;   + CTasks::STATE\_DEFERRED = 6;   + CTasks::STATE\_DECLINED = 7; * **STATUS** - статус для сортировки. Аналогичен **REAL\_STATUS**, но имеет дополнительно два мета статуса:   + **-2** - не просмотренная задача;   + **-1** - просроченная задача. * **MARK** - оценка; * **XML\_ID** - внешний код; * **SITE\_ID** - идентификатор сайта; * **ADD\_IN\_REPORT** - задача в отчете (Y|N); * **DATE\_START** - дата начала выполнения; * **DEADLINE** - крайний срок; * **CREATED\_DATE** - дата создания; * **CLOSED\_DATE** - дата завершения; * **CHANGED\_DATE** - дата последнего изменения; * **ACCOMPLICE** - идентификатор соисполнителя; * **AUDITOR** - идентификатор аудитора; * **DEPENDS\_ON** - идентификатор предыдущей задачи; * **ONLY\_ROOT\_TASKS** -  только корневые задачи (Y|N); * **SUBORDINATE\_TASKS** -  задачи текущего пользователя и его подчиненных (Y|N); * **OVERDUED** -  были просрочены (Y|N); * **DEPARTMENT\_ID** - идентификатор отдела.  Перед названием фильтруемого поля может указать тип фильтрации:  * "!" - не равно * "<" - меньше * "<=" - меньше либо равно * ">" - больше * ">=" - больше либо равно    "*значения фильтра*" - одиночное значение или массив.     Необязательный. По умолчанию записи не фильтруются. |  |
| *arSelect* | Массив возвращаемых полей задачи. |  |
| *arParams* | Массив дополнительных параметров. Необязательный. | 12.5.0 |

#### Возвращаемое значение

Возвращается объект [CDBResult](http://dev.1c-bitrix.ru/api_help/main/reference/cdbresult/index.php "CDBResult").

### Примеры использования

```
<?
// Выбираем все задачи пользователя с ID = 2
if (CModule::IncludeModule("tasks"))
{
	$res = CTasks::GetList(
		Array("TITLE" => "ASC"), 
		Array("RESPONSIBLE_ID" => "2")
	);
	while ($arTask = $res->GetNext())
	{
		echo "Task name: ".$arTask["TITLE"]."
";
	}
}
?>Копировать
```

  

```
<?
// Выбираем задачи, для которых пользователь является исполнителем или соисполнителем
$arFilter = array(
	'::LOGIC' => 'AND',
	'CHECK_PERMISSIONS' => 'Y',
	'ONLY_ROOT_TASKS' => 'Y',
	'SAME_GROUP_PARENT' => 'Y',
	'::SUBFILTER-1' => array(
		'::LOGIC' => 'OR',
		'::SUBFILTER-1' => array(
		'ACCOMPLICE' => array($USER->GetID()),
		'REAL_STATUS' => array(CTasks::STATE_NEW, CTasks::STATE_PENDING, CTasks::STATE_IN_PROGRESS),
		),
		'::SUBFILTER-2' => array(
			'RESPONSIBLE_ID' => $USER->GetID(),
			'REAL_STATUS' => array(CTasks::STATE_NEW, CTasks::STATE_PENDING, CTasks::STATE_IN_PROGRESS),
		),
	),
);
?>Копировать
```

Новинки документации в соцсетях: