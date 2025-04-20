[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormOutput](/api_help/form/classes/cformoutput/index.php)

isInputCaptionImage (5.1.1)

isInputCaptionImage
===================

```
bool
CFormOutput::isInputCaptionImage(
	string FIELD_SID
);Копировать
```

Проверка условия "прикреплена ли к вопросу с данным идентификатором картинка". Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *FIELD\_SID* | Строковой идентификатор поля вопроса. Обязательный параметр. |

#### Возвращаемое значение

*true*, если к вопросу прикреплена картинка. *false* в противном случае.

#### Использование

```
<?=$FORM->ShowInputCaption('MYFIELD_5')?>:
<?=$FORM->ShowInput('MYFIELD_5')?><br />
<?if($FORM->isInputCaptionImage('MYFIELD_5')):?>
	<?=$FORM->ShowInputCaptionImage('MYFIELD_5')?>
<?else:?>
	<?=CFile::ShowImage("/myimages/form_field_default.jpg")?>
<?endif?>:
Копировать
```

#### Смотрите также

- [Класс CFormOutput](/api_help/form/classes/cformoutput/index.php)
- [CFile::ShowImage](/api_help/main/reference/cfile/showimage.php)
- [CFormOutput::ShowInput](/api_help/form/classes/cformoutput/showinput.php)
- [CFormOutput::ShowInputCaption](/api_help/form/classes/cformoutput/showinputcaption.php)
- [CFormOutput::ShowInputCaptionImage](/api_help/form/classes/cformoutput/showinputcaptionimage.php)

Новинки документации в соцсетях: