[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogImage](/api_help/blogs/classes/cblogimage/index.php)

AddImageResizeHandler

AddImageResizeHandler
=====================

```
bool
CBlogImage::AddImageResizeHandler(
	array arParams
);Копировать
```

Метод регистрирует в качестве события `main.file.input.upload` метод **CBlogImage::ImageResizeHandler**. Полученные методом параметры будут переданы обработчику события при вызове. Метод статический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arParams | Массив параметров, которые будут переданы в обработчик события. |

#### Примеры использования

```
CBlogImage::AddImageResizeHandler(array("width" => 400, "height" => 400));Копировать
```

Новинки документации в соцсетях: