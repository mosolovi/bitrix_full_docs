[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogImage](/api_help/blogs/classes/cblogimage/index.php)

ImageResizeHandler

ImageResizeHandler
==================

```
bool
CBlogImage: ImageResizeHandler(
	array arCustomFile
	array arParams
);Копировать
```

Обработчик события `main.file.input.upload`. Регистрируется с помощью метода [CBlogImage::AddImageResizeHandler](/api_help/blogs/classes/cblogimage/addimageresizehandler.php).
Метод вызывается только при срабатывание события, применять его отдельно бессмысленно.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| arCustomFile | Массив с параметрами загруженного файла. Передается из события `main.file.input.upload` |
| arParams | Массив полей, переденный при регистрации обработчика. |

Новинки документации в соцсетях: