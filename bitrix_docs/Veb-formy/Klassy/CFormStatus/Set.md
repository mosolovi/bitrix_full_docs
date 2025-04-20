[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormStatus](/api_help/form/classes/cformstatus/index.php)

Set (4.0.4)

Set
===

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
mixed
CFormStatus::Set(
	array fields,
	mixed status_id = false,
	string check_rights = "Y"
)Копировать
```

Добавляет новый [статус](/api_help/form/terms.php#status) или обновляет существующий. Возвращает ID обновленного или добавленного [статуса](/api_help/form/terms.php#status) в случае положительного результата, в противном случае - "false". Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *fields* | Массив значений, в качестве ключей массива допустимы:  * **FORM\_ID**\* - ID [веб-формы](/api_help/form/terms.php#form); * **TITLE**\* - заголовок [статуса](/api_help/form/terms.php#status); * **C\_SORT** - порядок сортировки; * **ACTIVE** - флаг активности; допустимы следующие значения:   + **Y** - ответ активен;   + **N** - ответ не активен (по умолчанию). * **DESCRIPTION** - описание [статуса](/api_help/form/terms.php#status); * **CSS** - имя CSS класса для вывода заголовка [статуса](/api_help/form/terms.php#status); * **HANDLER\_OUT** - путь относительно корня к [обработчику](/api_help/form/status_processing.php), вызываемому при смене у [результата](/api_help/form/terms.php#result) данного [статуса](/api_help/form/terms.php#status) на какой либо другой; * **HANDLER\_IN** - путь относительно корня к [обработчику](/api_help/form/status_processing.php), вызываемому при смене у [результата](/api_help/form/terms.php#result) какого либо [статуса](/api_help/form/terms.php#status) на данный; * **DEFAULT\_VALUE** - флаг установки [статуса](/api_help/form/terms.php#status) по умолчанию, допустимы следующие значения:   + **Y** - статус будет устанавливаться;   + **N** - статус не будет устанавливаться (по умолчанию). * **arPERMISSION\_VIEW**\* - массив ID групп пользователей, имеющих [право](/api_help/form/permissions.php#result) "Просмотр результатов в данном статусе"; * **arPERMISSION\_MOVE**\* - массив ID групп пользователей, имеющих [право](/api_help/form/permissions.php#result) "Перевод результатов в данный статус"; * **arPERMISSION\_EDIT**\* - массив ID групп пользователей, имеющих [право](/api_help/form/permissions.php#result) "Редактирование результатов в данном статусе"; * **arPERMISSION\_DELETE**\* - массив ID групп пользователей, имеющих [право](/api_help/form/permissions.php#result) "Удаление результатов в данном статусе".   \* - обязательно к заполнению.  \* - в данных массивах может быть элемент со значением "0", означающий создателя [результата](/api_help/form/terms.php#result). |
| *status\_id* | ID обновляемого [статуса](/api_help/form/terms.php#status).  Параметр необязательный. По умолчанию - "false" (добавление нового [статуса](/api_help/form/terms.php#status)). |
| *check\_rights* | Флаг необходимости проверки прав текущего пользователя. Возможны следующие значения:  * **Y** - права необходимо проверить; * **N** - право не нужно проверять.  Для обновления статуса, либо создания нового статуса необходимо иметь право **[30] Полный доступ** на форму указанную в *fields*["FORM\_ID"].   Параметр необязательный. По умолчанию - "Y" (права необходимо проверить). |

### Смотрите также

* [Поля CFormStatus](/api_help/form/classes/cformstatus/index.php)

### Примеры использования

```
<?
$FORM_ID = 4; // ID веб-формы
$arFields = array(
	"FORM_ID"             => $FORM_ID,               // ID веб-формы
	"C_SORT"              => 100,                    // порядок сортировки
	"ACTIVE"              => "Y",                    // статус активен
	"TITLE"               => "Опубликовано",         // заголовок статуса
	"DESCRIPTION"         => "Окончательный статус", // описание статуса
	"CSS"                 => "statusgreen",          // CSS класс
	"HANDLER_OUT"         => "",                     // обработчик
	"HANDLER_IN"          => "",                     // обработчик
	"DEFAULT_VALUE"       => "N",                    // не по умолчанию
	"arPERMISSION_VIEW"   => array(2),               // право просмотра для всех
	"arPERMISSION_MOVE"   => array(),                // право перевода только админам
	"arPERMISSION_EDIT"   => array(),                // право редактирование для админам
	"arPERMISSION_DELETE" => array(),                // право удаления только админам
);
$NEW_ID = CFormStatus::Set($arFields);
if ($NEW_ID>0) echo "Успешно добавлен ID=".$NEW_ID;
else // ошибка
{
	// выводим текст ошибки
	global $strError;
	echo $strError;
}
?>Копировать
```

Новинки документации в соцсетях: