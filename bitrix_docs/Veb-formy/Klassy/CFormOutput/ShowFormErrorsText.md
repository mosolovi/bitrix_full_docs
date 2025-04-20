[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormOutput](/api_help/form/classes/cformoutput/index.php)

ShowFormErrorsText (5.1.1)

ShowFormErrorsText
==================

```
string
CFormOutput::ShowFormErrorsText(
);Копировать
```

Вывод неотформатированных ошибок валидатора формы. Метод нестатический.

#### Параметры метода

Нет параметров.

#### Возвращаемое значение

Возвращает неотфоматированный список ошибок валидатора формы. Если ошибок
нет, возвращается пустая строка.

#### Использование

```
<font color="#FF0000"><?=$FORM->ShowFormErrorsText()?></font>Копировать
```

#### Смотрите также

- [Класс CFormOutput](/api_help/form/classes/cformoutput/index.php)
- [CFormOutput::ShowFormErrors](/api_help/form/classes/cformoutput/showformerrors.php)
- [CFormOutput::isFormErrors](/api_help/form/classes/cformoutput/isformerrors.php)

Новинки документации в соцсетях: