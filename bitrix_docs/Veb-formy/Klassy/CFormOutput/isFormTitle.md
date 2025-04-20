[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormOutput](/api_help/form/classes/cformoutput/index.php)

isFormTitle (5.1.1)

isFormTitle
===========

```
bool
CFormOutput::isFormTitle(
);Копировать
```

Проверка условия "есть ли у формы текстовый заголовок (название)". Метод нестатический.

#### Параметры метода

Нет параметров.

#### Возвращаемое значение

*true*, если у формы есть текстовый заголово (название). *false* в противном случае.

#### Использование

```
<?if($FORM->isFormTitle()):?>Описание: <?=$FORM->ShowFormTitle()?><?endif?>
Копировать
```

#### Смотрите также

- [Класс CFormOutput](/api_help/form/classes/cformoutput/index.php)
- [CFormOutput::ShowFormTitle](/api_help/form/classes/cformoutput/showformtitle.php)

Новинки документации в соцсетях: