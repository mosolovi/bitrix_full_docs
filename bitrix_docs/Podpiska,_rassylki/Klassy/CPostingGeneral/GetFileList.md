[Подписка, рассылки](/api_help/subscribe/index.php)

[Классы](/api_help/subscribe/classes/index.php)

[CPostingGeneral](/api_help/subscribe/classes/cpostinggeneral/index.php)

GetFileList (доступен с 4.0.5)

GetFileList
===========

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
CDBResult
CPosting::GetFileList(
	int ID,
	int file_id = false
);Копировать
```

Метод возвращает выборку вложений выпуска. Метод статический.

#### Параметры

| Параметр | Описание | С версии |
| --- | --- | --- |
| ID | Идентификатор выпуска. |  |
| file\_id | Идентификатор вложения. Если параметр не указан или равен false, то выбираются все вложения выпуска. |  |

#### Возвращаемые значения

Возвращается результат запроса типа [CDBResult](/api_help/main/reference/cdbresult/index.php). При выборке из результата методами класса CDBResult
становятся доступны [поля объекта "Файл"](/api_help/main/reference/cfile/index.php): ID, FILE\_SIZE, ORIGINAL\_NAME, SUBDIR, FILE\_NAME, CONTENT\_TYPE.

### Примеры использования

```
//размер всех вложений
$attach_size = 0;
$rsFile = CPosting::GetFileList($ID);
while($arFile = $rsFile->Fetch())
	$attach_size += $arFile["FILE_SIZE"];
Копировать
```

Новинки документации в соцсетях: