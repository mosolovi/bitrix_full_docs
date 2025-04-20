[Обучение](/api_help/learning/index.php)

[Классы](/api_help/learning/classes/index.php)

[CCourse](/api_help/learning/classes/ccourse/index.php)

SetPermission (доступен с 5.0.3)

SetPermission
=============

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
CCourse::SetPermission(
	int COURSE_ID,
	array arPERMISSIONS
);Копировать
```

**Важно!** Данный метод устарел, использовать его крайне не рекомендуется. Он оставлен лишь для обратной совместимости.

Метод устанавливает права доступа *arPERMISSIONS* для учебного курса с идентификатором *COURSE\_ID*. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| COURSE\_ID | Идентификатор курса. |
| arPERMISSIONS | массив вида Array("код группы"=>"право доступа", ....), где *право доступа*:  * D - доступ запрещён; * R - чтение; * W - запись; * X - полный доступ (запись + назначение прав доступа на данный курс). |

### Смотрите также

* [CCourse](/api_help/learning/classes/ccourse/index.php)::[GetPermission](/api_help/learning/classes/ccourse/getpermission.php)
* [CCourse](/api_help/learning/classes/ccourse/index.php)::[Update()](/api_help/learning/classes/ccourse/update.php)

### Примеры использования

```
<?
CCourse::SetPermission($COURSE_ID, Array("2"=>"R", "3"=>"W"));
?>Копировать
```

Новинки документации в соцсетях: