[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlock](/api_help/iblock/classes/ciblock/index.php)

GetPermission (доступен с 3.0.3)

GetPermission
=============

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
string
CIBlock::GetPermission(
	int IBLOCK_ID,
	int FOR_USER_ID = false
);Копировать
```

Возвращает право доступа к информационному блоку *IBLOCK\_ID* для пользователя с кодом *FOR\_USER\_ID* или для текущего пользователя (если код не задан). Нестатический метод.

**Примечание:** метод считается устаревшим (не работает при использовании расширенных прав). Рекомендуется использовать **CIBlockElementRights::UserHasRightTo** и **CIBlockSectionRights::UserHasRightTo**.

#### Параметры вызова

| Параметр | Описание | С версии |
| --- | --- | --- |
| IBLOCK\_ID | Код информационного блока. |  |
| FOR\_USER\_ID | Код пользователя. Необязательный параметр.   До версии 11.5.1 параметр назывался USER\_ID. | 8.5.0 |

#### Возвращаемое значение

Символ права доступа:  
"D" - запрещён,  
"R" - чтение,  
"U" - изменение через документооборот,  
"W" - изменение,  
"X" - полный доступ (изменение + право изменять права доступа).

### Смотрите также

* [CIBlock::GetGroupPermissions](/api_help/iblock/classes/ciblock/getgrouppermissions.php)
* [CUser::GetUserGroupString](/api_help/main/reference/cuser/getusergroupstring.php)

### Примеры использования

```
<?
$iblock_permission = CIBlock::GetPermission($id);
if($iblock_permission<"X")
	return false;
?>Копировать
```

Пример получения уровня доступа с расширенным управлением правами:

```
$tRight = 'element_edit';
$canEdit = CIBlockElementRights::UserHasRightTo($IBLOCK_ID, $ELEMENT_ID, $tRight);
if (!$tRight) echo "access denied";Копировать
```

$tRight может принимать значения:

**section\_element\_bind** - Добавление элемента в раздел (создание элемента)  
**element\_bizproc\_start** - Запуск бизнес-процесса для элемента  
**iblock\_edit** - Изменение параметров инфоблока  
**iblock\_rights\_edit** - Изменение прав доступа к инфоблоку  
**section\_rights\_edit** - Изменение прав доступа к разделу  
**element\_rights\_edit** - Изменение прав доступа к элементу  
**section\_edit** - Изменение раздела  
**element\_edit** - Изменение элемента  
**element\_edit\_any\_wf\_status** - Изменение элемента в любом статусе документооборота  
**iblock\_admin\_display** - Показ инфоблока в административном разделе  
**element\_edit\_price** - Редактирование цен, относящихся к элементу  
**section\_section\_bind** - Создание подраздела в разделе  
**iblock\_delete** - Удаление инфоблока  
**section\_delete** - Удаление раздела  
**element\_delete** - Удаление элемента  
**section\_read** - Чтение параметров раздела  
**element\_read** - Чтение элемента  
**iblock\_export** - Экспорт инфоблока.

Новинки документации в соцсетях: