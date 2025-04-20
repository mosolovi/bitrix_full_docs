[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormOutput](/api_help/form/classes/cformoutput/index.php)

isFormDescription (5.1.1)

isFormDescription
=================

```
bool
CFormOutput::isFormDescription(
);Копировать
```

Проверка условия "есть ли у формы текстовое описание". Метод нестатический.

#### Параметры метода

Нет параметров.

#### Возвращаемое значение

*true*, если у формы есть текстовое описание. *false* в противном
случае.

#### Использование

```
<?if($FORM->isFormDescription()):?>Описание: <?=$FORM->ShowFormDescription()?><?endif?>Копировать
```

#### Смотрите также

[Класс CFormOutput](/api_help/form/classes/cformoutput/index.php)  
[CFormOutput::ShowFormDescription](/api_help/form/classes/cformoutput/showformdescription.php)

Новинки документации в соцсетях: