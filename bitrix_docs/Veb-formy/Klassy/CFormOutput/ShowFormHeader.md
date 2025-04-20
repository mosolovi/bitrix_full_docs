[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormOutput](/api_help/form/classes/cformoutput/index.php)

ShowFormHeader (5.1.1)

ShowFormHeader
==============

```
string
CFormOutput::ShowFormHeader(
);Копировать
```

Вывод HTML-заголовка формы. Метод нестатический.

#### Параметры метода

Нет параметров.

#### Возвращаемое значение

Возвращает HTML-код заголовка формы. В том числе, тэг <form>, скрытые поля.

#### Использование

При создании шаблона формы редактором, добавляется в начало шаблона автоматически.

```
<?=$FORM->ShowFormHeader()?>
Копировать
```

#### Смотрите также

- [Класс CFormOutput](/api_help/form/classes/cformoutput/index.php)
- [CFormOutput::ShowFormFooter](/api_help/form/classes/cformoutput/showformfooter.php)

Новинки документации в соцсетях: