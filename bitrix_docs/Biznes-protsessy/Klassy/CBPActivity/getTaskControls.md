[Бизнес-процессы](/api_help/bizproc/index.php)

[Классы](/api_help/bizproc/bizproc_classes/index.php)

[CBPActivity](/api_help/bizproc/bizproc_classes/CBPActivity/index.php)

getTaskControls

getTaskControls
===============

Включить вкладки

Описание и параметры

Пример ответа

### Описание и параметры

```
public static function getTaskControls($arTask)
{
	return CBPActivity::CallStaticMethod(
		$arTask["ACTIVITY"],
		"getTaskControls",
		array(
			$arTask
		)
	)
}Копировать
```

Метод возвращает массив элементов формы задания: кнопки и поля.

**Примечание:** Метод принимает массив конфигурационных параметров и генерирует скрипты, необходимые для показа файлового диалога. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *$arTask* | Массив с параметрами задания. |

### Пример ответа

```
Array (
    [BUTTONS] => Array (
        [0] => Array (
            [TYPE] => submit
            [TARGET_USER_STATUS] => 3
            [NAME] => approve
            [VALUE] => Y
            [TEXT] => Сохранить
        )
    )
    [FIELDS] => Array (
        [0] => Array (
            [Id] => contractor
            [Type] => E:ECrm
            [Name] => Подрядчик
            [Description] => Кто выполняет работы
            [Multiple] =>
            [Required] => 1
            [Options] =>
            [Settings] =>
            [Default] => Array (
                [0] => CO_5
            )
            [FieldId] => bpriact_contractor
        )
        [1] => Array (
            [Id] => phone_number
            [Type] => string
            [Name] => Номер телефона
            [Description] => Номер телефона бригадира
            [Multiple] =>
            [Required] => 1
            [Options] =>
            [Settings] =>
            [Default] =>
            [FieldId] => bpriact_phone_number
        )
        [2] => Array (
            [Id] => task_comment
            [Type] => text
            [Name] => Комментарий
            [Required] => 1
        )
    )
)Копировать
```

Возвращаемые данные в массиве `Fields`

| Ключ | Описание |
| --- | --- |
|  |  |
| --- | --- |
| `Id` | Символьный идентификатор поля |
| `Type` | Тип поля. Базовые значения:  * `bool` — да или нет * `date` — дата * `datetime` — дата и время * `double` — число * `int` — целое число * `select` — список * `string` — строка * `text` — текст * `user` — пользователь   Остальные типы зависят от документа, с которым работает бизнес-процесс |
| `Name` | Наименование поля |
| `Description` | Описание поля |
| `Multiple` | Множественность поля. Может иметь значение `1` или `0` |
| `Required` | Обязательность параметра. Может иметь значение `1` или `0` |
| `Options` | Настройки поля. Значения зависят от типа параметра. Например, для типа Список `select` это варианты значений списка |
| `Settings` | Дополнительные настройки поля |
| `Default` | Значение поля по умолчанию |
| `FieldId` | Уникальный идентификатор поля в системе. Обычно формируется как префикс действия + `Id` |

Новинки документации в соцсетях: