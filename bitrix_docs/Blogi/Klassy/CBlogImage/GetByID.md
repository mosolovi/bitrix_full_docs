[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogImage](/api_help/blogs/classes/cblogimage/index.php)

GetByID

GetByID
=======

```
array
CBlogImage::GetByID(
	int ID
);Копировать
```

Метод возвращает параметры изображения с идентификатором *ID*. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| ID | Идентификатор изображения. |

#### Возвращаемое значение

Возвращается массив с [полями изображения](/api_help/blogs/classes/cblogimage/add.php#array).

#### Примеры использования

Получение информации об изображении с идентификатором 16

```
$res = CBlogImage::GetByID(16);
if($res)
	print_r($res);Копировать
```

Новинки документации в соцсетях: