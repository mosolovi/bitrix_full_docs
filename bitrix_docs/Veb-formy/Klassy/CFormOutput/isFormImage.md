[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormOutput](/api_help/form/classes/cformoutput/index.php)

isFormImage (5.1.1)

isFormImage
===========

```
bool
CFormOutput::isFormImage(
);Копировать
```

Проверка условия "прикреплена ли к форме картинка". Метод нестатический.

#### Параметры метода

Нет параметров.

#### Возвращаемое значение

*true*, если к форме прикреплена картинка. *false* в противном случае.

#### Использование

```
<?if($FORM->isFormImage()):?>
<?=$FORM->ShowFormImage()?>
<?else:?>
<?=CFile::ShowImage("/myimages/form_default.jpg")?>
<?endif?>
Копировать
```

#### Смотрите также

- [Класс CFormOutput](/api_help/form/classes/cformoutput/index.php)
- [CFile::ShowImage](/api_help/main/reference/cfile/showimage.php)
- [CFormOutput::ShowFormImage](/api_help/form/classes/cformoutput/showformimage.php)

Новинки документации в соцсетях: