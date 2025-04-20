[Форум](/api_help/forum/index.php)

[Классы](/api_help/forum/developer/index.php)

[CForumUser](/api_help/forum/developer/cforumuser/index.php)

GetByIDEx (доступно с 3.3.3)

GetByIDEx
=========

```
array
CForumUser::GetByIDEx(
	int ID,
	arAddParams = array()
);Копировать
```

Возвращает массив параметров профайла, а так же сопутствующие параметры, по его коду *ID*. Метод статический.

#### Параметры функции

| Параметр | Описание | C версии |
| --- | --- | --- |
| ID | Код профайла. |  |
| arAddParams | Массив параметров. | 12.0.0 |

#### Возвращаемое значение

Массив параметров профайла, включая сопутствующие. Если профайл не найден, то возвращается значение false.

#### Смотрите также

* [Поля профайла](/api_help/forum/fields.php#cforumuser)

Новинки документации в соцсетях: