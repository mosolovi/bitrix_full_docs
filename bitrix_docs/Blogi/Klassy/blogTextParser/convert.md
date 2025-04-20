[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[blogTextParser](/api_help/blogs/classes/blogtextparser/index.php)

convert

convert
=======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
string
convert(
	string text,
	bool   bPreview = true,
	array  arImages = array(),
	array  arAllow = array(
		"HTML" =>   "N", 
		"ANCHOR" => "Y", 
		"BIU" =>    "Y", 
		"IMG" =>    "Y", 
		"QUOTE" =>  "Y", 
		"CODE" =>   "Y", 
		"FONT" =>   "Y", 
		"LIST" =>   "Y", 
		"SMILES" => "Y", 
		"NL2BR" =>  "N"
	)
);Копировать
```

Метод форматирует текст *text* в соответствии с параметрами *bPreview, arImages, arAllow*. Метод нестатический.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| text | Исходный текст сообщения. |  |
| bPreview | Флаг - обрезать ли текст для просмотра (по тегу [CUT]).  Необязательный. По умолчанию *true* - текст будет обрезан до тега [CUT]. |  |
| arImages | Массив вида *array(array(IMAGE\_ID, FILE\_ID)[, ...])*.  * IMAGE\_ID - идентификaтор изображения в сообщении; * FILE\_ID - идентификатор файла этого изображения.  Необязательный. По умолчания теги изображений не будут заменяться. |  |
| arAllow | Массив параметров форматирования сообщения. Необязательный параметр. Допустимы следующие параметры:  * `HTML` - в тексте могут содержаться любые HTML теги * `ANCHOR` - разрешен тег <a>; * `BIU` - разрешены теги <b>, <i>, <u>; * `IMG` - разрешен тег <img>; * `QUOTE` - разрешен тег цитирования <quote>; * `CODE` - разрешен тег показа кода <code>; * `FONT` - разрешен тег <font>; * `LIST` - разрешены теги <ul>, <li>; * `SMILES` - показ смайликов в виде картинок; * `NL2BR` - заменять переводы каретки на тег <br> при разрешении принимать любые HTML теги; * `VIDEO`; * `TABLE`; * `CUT_ANCHOR`; `SHORT_ANCHOR`. Параметры могут принимать значения *Y* и *N*. |  |
| type | Необязательный параметр. Значение по умолчанию - "html". Удален с версии 10.0.0 | 9.0.0 |
| arParams | Необязательный параметр. | 12.0.0 |

#### Возвращаемое значение

Метод возвращает отформатированное сообщение.

### Примеры использования

```
<?
$arPost = CBlogPost::GetByID(3);
$p = new blogTextParser();
$res = CBlogImage::GetList(
	array("ID"=>"ASC"),
	array(
		"POST_ID"=>$arPost['ID'], 
		"BLOG_ID"=>$arPost['BLOG_ID']
	)
);
while ($arImage = $res->Fetch())
	$arImages[$arImage['ID']] = $arImage['FILE_ID'];
$text = $p->convert($arPost["DETAIL_TEXT"], false, $arImages);
?>Копировать
```

Новинки документации в соцсетях: