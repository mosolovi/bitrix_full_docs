[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockType](/api_help/iblock/classes/ciblocktype/index.php)

Delete (доступен с 3.1.3)

Delete
======

```
bool
CIBlockType::Delete(
	string ID
);Копировать
```

Метод удаляет тип информационных блоков по его коду *ID*. Также удаляются все информационные блоки указанного типа. Метод статический.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | Код типа. |

#### Возвращаемое значение

Возвращается true в случае успешного удаления, иначе возвращает false.

#### Смотрите также

* [CIBlock::Delete](/api_help/iblock/classes/ciblock/delete.php)

#### Примеры использования

```
<?
$DB->StartTransaction();
if(!CIBlockType::Delete('catalog'))
{
	$DB->Rollback();
	echo 'Delete error!';
}
$DB->Commit();
?>Копировать
```

Новинки документации в соцсетях: