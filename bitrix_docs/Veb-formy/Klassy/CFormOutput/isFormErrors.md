[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormOutput](/api_help/form/classes/cformoutput/index.php)

isFormErrors (5.1.1)

isFormErrors
============

```
bool
CFormOutput::isFormErrors(
);Копировать
```

Проверка условия "есть ли ошибки валидатора формы". Метод нестатический.

#### Параметры метода

Нет параметров.

#### Возвращаемое значение

*true*, если в процессе обработки результата формы обнаружены ошибки. *false* в противном случае.

#### Использование

```
<?if($FORM->isFormErrors()):?>Ошибки: <?=$FORM->ShowFormErrors()?><?endif?>
Копировать
```

#### Смотрите также

- [Класс CFormOutput](/api_help/form/classes/cformoutput/index.php)
- [CFormOutput::ShowFormErrors](/api_help/form/classes/cformoutput/showformerrors.php)
- [CFormOutput::ShowFormErrorsText](/api_help/form/classes/cformoutput/showformerrorstext.php)

Новинки документации в соцсетях: