[Wiki](/api_help/wiki/index.php)

[Классы](/api_help/wiki/classes/index.php)

[CWiki](/api_help/wiki/classes/cwiki/index.php)

DeleteImage (9.5.1)

DeleteImage
===========

```
void
CWiki::DeleteImage(
	int IMAGE_ID,
	int ID,
	int IBLOCK_ID
);Копировать
```

Удаляет изображение из Wiki-страницы. Нестатический метод.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| IMAGE\_ID | Идентификатор изображения. |  |
| ID | Идентификатор Wiki-страницы. До версии 10.0.0 назывался **ELEMENT\_ID** |  |
| IBLOCK\_ID | Идентификатор Инфоблока. |  |

#### Смотрите также

* [CWiki::AddImage](/api_help/wiki/classes/cwiki/AddImage.php)

#### Примеры использования

```
<?
// Удалим изображение с идентификатором 5 из страницы с идентификатором 13 из инфоблока с идентификатором 2
$IMAGE_ID = 5;
$ID = 13;
$IBLOCK_ID = 2;
$CWiki = new CWiki();
$CWiki->DeleteImage($IMAGE_ID, $ID, $IBLOCK_ID);
?>Копировать
```

Новинки документации в соцсетях: