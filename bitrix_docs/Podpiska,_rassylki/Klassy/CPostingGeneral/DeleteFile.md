[Подписка, рассылки](/api_help/subscribe/index.php)

[Классы](/api_help/subscribe/classes/index.php)

[CPostingGeneral](/api_help/subscribe/classes/cpostinggeneral/index.php)

DeleteFile (доступен с 4.0.5)

DeleteFile
==========

```
CPosting::DeleteFile(
	int ID,
	int file_id = false
);Копировать
```

Метод удаляет одно или все вложения выпуска. Метод статический.

#### Параметры

| Параметр | Описание | С версии |
| --- | --- | --- |
| ID | Идентификатор выпуска. |  |
| file\_id | Идентификатор вложения. Если параметр не указан или равен false, то удаляются все вложения выпуска. |  |

#### Возвращаемые значения

Нет.

#### Пример использования

```
if(is_array($FILE_ID))
	foreach($FILE_ID as $file_id)
		CPosting::DeleteFile($ID, $file_id);Копировать
```

Новинки документации в соцсетях: