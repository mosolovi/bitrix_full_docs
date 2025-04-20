[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnBeforeChangeFile (с версии 8.5.1)

OnBeforeChangeFile
==================

Включить вкладки

Описание и параметры

Смотрите также

Пример функции-обработчика

### Описание и параметры

```
bool функция-обработчик(
	string abs_path,
	string &strContent
);Копировать
```

Событие "OnBeforeChangeFile" вызывается при изменении файла методом [$APPLICATION->SaveFileContent](/api_help/main/reference/cmain/savefilecontent.php), перед его сохранением. Событие добавлено в версии 8.5.1 ядра. Контент в событие передается по ссылке.

#### Возвращаемое значение

При возврате true поизводится сохранение файла. При возврате false сохранение файла отменяется.

#### Параметры

| Параметр | Описание |
| --- | --- |
| *abs\_path* | Абсолютный путь к файлу (включая document\_root). |
| *strContent* | Новое содержимое файла. Значение передается по ссылке. Таким образом, обработчик может изменить содержимое файла перед его сохранением. |

### Смотрите также

* [Событие "OnChangePermissions"](/api_help/main/events/onchangepermissions.php)
* [CMain::SaveFileContent](/api_help/main/reference/cmain/savefilecontent.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Пример функции-обработчика

```
// файл /bitrix/php_interface/init.php
AddEventHandler("main", "OnBeforeChangeFile", "MyBeforeChangeFile");
public static function MyBeforeChangeFile($abs_path, $content)
{
	if(strpos($content, "Вася") !== false)
	{
		$GLOBALS['APPLICATION']->ThrowException("Вы не можете сохранять слово 'Вася' в документе! (".$abs_path.")");
		return false;
	}
	return true;
}
Копировать
```

Новинки документации в соцсетях: