[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlock](/api_help/iblock/classes/ciblock/index.php)

SetPermission (доступен с 3.0.3)

SetPermission
=============

```
CIBlock::SetPermission(
	int IBLOCK_ID,
	array arPERMISSIONS
);Копировать
```

Метод устанавливает права доступа *arPERMISSIONS* для информационного блока *IBLOCK\_ID*. Перед этим все права установленные ранее снимаются. Права устанавливаются только для инфоблоков с простыми правами. Cтатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| IBLOCK\_ID | Код информационного блока. |
| arPERMISSIONS | Массив вида Array("код группы"=>"право доступа", ....), где *право доступа*:   E - Добавление элементов инфоблока в публичной части,  S - Просмотр элементов и разделов в административной части,  T - Добавление элементов инфоблока в административной части,   R - чтение,   U - редактирование через документооборот,   W - запись,   X - полный доступ (запись + назначение прав доступа на данный инфоблок). |

#### Смотрите также

* [CIBlock](/api_help/iblock/classes/ciblock/index.php)::[GetPermission()](/api_help/iblock/classes/ciblock/getpermission.php)
* [CIBlock](/api_help/iblock/classes/ciblock/index.php)::[Update()](/api_help/iblock/classes/ciblock/update.php)

#### Примеры использования

```
<?
CIBlock::SetPermission($IBLOCK_ID, Array("1"=>"X", "2"=>"R", "3"=>"W"));
?>Копировать
```

Новинки документации в соцсетях: