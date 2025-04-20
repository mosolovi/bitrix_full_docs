[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumSubscribe](/api_help/forum/developer/cforumsubscribe/index.php)

Delete (доступен с 3.3.3)

Delete
======

```
bool
Delete(
	int ID
);Копировать
```

Удаляет подписку с кодом *ID*. Метод статический.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| ID | Код подписки, которую необходимо удалить. |

#### Возвращаемое значение

Возвращает объект [CDBResult](/api_help/main/reference/cdbresult/index.php).

#### Смотрите также

* Перед удалением подписки следует проверить возможность удаления методом [CForumSubscribe::CanUserDeleteSubscribe](/api_help/forum/developer/cforumsubscribe/canuserdeletesubscribe.php)

#### Пример

```
if (CModule::IncludeModule("forum"))
{
	$db_res = CForumSubscribe::Delete(1);
	?><pre><b>$db_res->AffectedRowsCount(): </b><?print_r($db_res->AffectedRowsCount())?></pre><?
}Копировать
```

Новинки документации в соцсетях: