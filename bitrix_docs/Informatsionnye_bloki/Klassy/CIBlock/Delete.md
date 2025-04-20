[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlock](/api_help/iblock/classes/ciblock/index.php)

Delete (доступен с 3.0.3)

Delete
======

```
bool
CIBlock::Delete(
	int ID
);Копировать
```

Метод удаляет информационный блок. Метод статический.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | Код информационного блока. |

#### Возвращаемое значение

Возвращается true в случае успешного удаления и false - в противном случае. Удаление можно отменить в обработчике события [OnBeforeIBlockDelete](/api_help/iblock/events/onbeforeiblockdelete.php).

#### Примеры использования

```
<?
if($USER->IsAdmin())
{
	$DB->StartTransaction();
	if(!CIBlock::Delete($iblock_id))
	{
		$strWarning .= GetMessage("IBLOCK_DELETE_ERROR");
		$DB->Rollback();
	}
	else
		$DB->Commit();
}
?>Копировать
```

Новинки документации в соцсетях: