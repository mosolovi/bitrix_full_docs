[Wiki](/api_help/wiki/index.php)

[Классы](/api_help/wiki/classes/index.php)

[CWiki](/api_help/wiki/classes/cwiki/index.php)

AddImage (9.5.1)

AddImage
========

```
int
CWiki::AddImage(
	int ID,
	int IBLOCK_ID,
	array arImage
);Копировать
```

Метод привязывает изображение к Wiki-странице. Нестатический метод.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| ID | Идентификатор Wiki-страницы. До версии 10.0.0 назывался **ELEMENT\_ID**. |  |
| IBLOCK\_ID | Идентификатор Инфоблока |  |
| arImage | Массив свойств изображения |  |

#### Смотрите также

* [CWiki::DeleteImage](/api_help/wiki/classes/cwiki/DeleteImage.php)

#### Примеры использования

```
<?
// привяжем изображение к странице с идентификатором 13 из инфоблока с идентификатором 2
$ID = 13;
$IBLOCK_ID = 2;
if (CFile::IsImage($_FILES['FILE_ID']['name']))
{
	$CWiki = new CWiki();
	$CWiki->AddImage($ID, $IBLOCK_ID, $_FILES['FILE_ID']);
}?>Копировать
```

Новинки документации в соцсетях: