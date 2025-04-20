[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

CIBlockXMLFile (доступен с 6.5.0)

CIBlockXMLFile
==============

Включить вкладки

Описание и список методов

Примеры использования

### Описание и список методов

**CIBlockXMLFile** - класс для работы с файлами XML.

#### Методы класса

| Метод | Описание | С версии |
| --- | --- | --- |
| [DropTemporaryTables](/api_help/iblock/classes/ciblockxmlfile/droptemporarytables.php) | Удаляет таблицы, содержащие ранее загруженный файл. | 6.5.0 |
| [GetFilePosition](/api_help/iblock/classes/ciblockxmlfile/getfileposition.php) | Возвращает объем прочитанных байт. | 6.5.0 |
| [CreateTemporaryTables](/api_help/iblock/classes/ciblockxmlfile/createtemporarytables.php) | Создает таблицы для загрузки XML. | 6.5.0 |
| [ReadXMLToDatabase](/api_help/iblock/classes/ciblockxmlfile/readxmltodatabase.php) | Загрузка данных из файла в таблицы БД (пошаговая). | 6.5.0 |
| [IndexTemporaryTables](/api_help/iblock/classes/ciblockxmlfile/indextemporarytables.php) | Индексация таблиц для ускорения доступа. | 6.5.0 |
| [safeUnZip](/api_help/iblock/classes/ciblockxmlfile/safeunzip.php) | Метод распаковывает ZIP-архив из файла *fileName*. | 23.100.0 |

### Примеры использования

```
<?
$obXMLFile = new CIBlockXMLFile;
// Удаляем результат предыдущей загрузки
$obXMLFile->DropTemporaryTables();
// Подготавливаем БД
if(!$obXMLFile->CreateTemporaryTables())
	return "Ошибка создания БД.";
if($fp = fopen($FILE_NAME, "rb"))
{
	// Чтение содержимого файла за один шаг
	$obXMLFile->ReadXMLToDatabase($fp, $NS, 0);
	fclose($fp);
}
else
{
	// Файл открыть не удалось
	return "Ошибка открытия файла";
}
// Индексируем загруженные данные для ускорения доступа
if(!CIBlockXMLFile::IndexTemporaryTables())
	return "Ошибка создания индексов БД.";
?>Копировать
```

Новинки документации в соцсетях: