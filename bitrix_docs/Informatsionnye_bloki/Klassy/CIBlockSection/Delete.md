[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockSection](/api_help/iblock/classes/ciblocksection/index.php)

Delete (доступен с 3.0.4)

Delete
======

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
bool CIBlockSection::Delete(
	int ID,
	bool bCheckPermissions = true
);Копировать
```

Метод удаляет раздел с кодом *ID*, вместе со всеми подразделами и элементами, которые привязаны только к этому разделу. Также удаляются значения свойств типа "Привязка к разделу" указывающие на удаляемый. При установленном модуле поиска раздел удаляется из поискового индекса. Перед удалением раздела вызываются обработчики события [OnBeforeIBlockSectionDelete](/api_help/iblock/events/onbeforeiblocksectiondelete.php) из которых можно отменить это действие. После удаления вызывается обработчик события OnAfterIBlockSectionDelete. Метод статический.

#### Параметры вызова

| Параметр | Описание | С версии |
| --- | --- | --- |
| ID | Код раздела. |  |
| bCheckPermissions | Флаг проверки прав доступа. Необязательный параметр. | 9.0.2 |

#### Возвращаемое значение

Возвращается true в случае успешного удаления, иначе возвращается false.

### Смотрите также

* [OnBeforeIBlockSectionDelete](/api_help/iblock/events/onbeforeiblocksectiondelete.php)
* OnAfterIBlockSectionDelete

### Примеры использования

```
<?
if(CIBlock::GetPermission($IBLOCK_ID)>='W')
{
	$DB->StartTransaction();
	if(!CIBlockSection::Delete($SECTION_ID))
	{
		$strWarning .= 'Error.';
		$DB->Rollback();
	}
	else
		$DB->Commit();
}
?>Копировать
```

Новинки документации в соцсетях: