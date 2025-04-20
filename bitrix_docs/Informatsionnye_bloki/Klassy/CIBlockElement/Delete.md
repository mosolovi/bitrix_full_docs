[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockElement](/api_help/iblock/classes/ciblockelement/index.php)

Delete (доступен с 3.0.5)

Delete
======

```
bool CIBlockElement::Delete(
	int ID
);Копировать
```

Метод удаляет элемент информационного блока. Также удаляются значения свойств типа "Привязка к элементу" указывающие на удаляемый. При установленном модуле поиска элемент удаляется из поискового индекса. Перед удалением вызываются обработчики события [OnBeforeIBlockElementDelete](/api_help/iblock/events/onbeforeiblockelementdelete.php) из которых можно отменить это действие. После удаления вызывается обработчик события OnAfterIBlockElementDelete. Метод статический.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | Код элемента. |

#### Возвращаемое значение

Возвращается true в случае успешного удаления, в противном случае метод вернет false.
  
При попытке удаления несуществующего элемента метод также вернет true.
  


#### Примеры использования

```
<?
if(CIBlock::GetPermission($IBLOCK_ID)>='W')
{
	$DB->StartTransaction();
	if(!CIBlockElement::Delete($ELEMENT_ID))
	{
		$strWarning .= 'Error!';
		$DB->Rollback();
	}
	else
		$DB->Commit();
}
?>Копировать
```

Новинки документации в соцсетях: