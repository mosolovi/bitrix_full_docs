[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnFileDelete (с версии 10.0.5)

OnFileDelete
============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
void
функция-обработчик(
	array arFile
);Копировать
```

Событие "OnFileDelete" вызывается после удаления файла в методе [CFile::Delete](/api_help/main/reference/cfile/delete.php). Событие может использоваться для удаления производной от файла информации (созданных при загрузке картинки эскизов и т.п.).

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| arFile | Массив с информацией об удаленном файле, содержащий ключи:   SUBDIR - подпапка в папке для загрузки файлов (обычно в /upload);   FILE\_NAME - имя удаленного файла. |

#### Возвращаемое значение

Не используется.

#### Смотрите также

* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Примеры использования

```
<?
AddEventHandler("main", "OnFileDelete", "MyOnFileDelete");
public static function MyOnFileDelete($arFile)
{
	$fname = $_SERVER["DOCUMENT_ROOT"]."/upload/resize/".$arFile["SUBDIR"]."/small_".$arFile["FILE_NAME"];
	if(file_exists($fname))
		unlink($fname);
}
?>Копировать
```

Новинки документации в соцсетях: