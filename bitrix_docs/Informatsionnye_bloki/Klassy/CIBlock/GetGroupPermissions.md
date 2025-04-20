[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlock](/api_help/iblock/classes/ciblock/index.php)

GetGroupPermissions (доступен с 3.0.3)

GetGroupPermissions
===================

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
array
CIBlock::GetGroupPermissions(
	int ID
);Копировать
```

Возвращает права доступа к информационному блоку ID для всех групп пользователей. Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | Код информационного блока. |

#### Возвращаемое значение

Массив прав вида Array("ID группы"=>"Право доступа"[, ...]).
Право доступа может принимать значение:  
"R" - чтение,  
"U" - изменение через документооборот,  
"W" - изменение,  
"X" - полный доступ (изменение + право изменять права доступа).

### Смотрите также

* [GetPermission](/api_help/iblock/classes/ciblock/getpermission.php)

### Примеры использования

```
<?
// выбор списка пользователей, имеющих право доступа на чтение инфоблока $IBLOCK_ID
$gr_res = CIBlock::GetGroupPermissions($IBLOCK_ID);
$res = Array(1);
foreach($gr_res as $group_id=>$perm)
if($perm>"R")
	$res[] = $group_id;
$res = CUser::GetList($by="NAME", $order="ASC", Array("GROUP_MULTI"=>$res));
?>Копировать
```

Новинки документации в соцсетях: