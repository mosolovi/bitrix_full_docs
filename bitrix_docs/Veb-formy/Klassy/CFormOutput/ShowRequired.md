[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormOutput](/api_help/form/classes/cformoutput/index.php)

ShowRequired (5.1.1)

ShowRequired
============

```
string
CFormOutput::ShowRequired(
);Копировать
```

Вывод пометки "обязательное поле" - \*. При выводе подписи к полю посредством [CFormOutput::ShowInputCaption](/api_help/form/classes/cformoutput/showinputcaption.php) пометка вставляется автоматически. Метод нестатический.

#### Параметры метода

Нет параметров.

#### Возвращаемое значение

Возвращается HTML-код пометки

#### Использование

```
Первый обязательный вопрос <?=$FORM->ShowRequired()?>:<?=$FORM->ShowInput('REQ_FIELD_1')?><br />
<?=$FORM->ShowInputCaption('REQ_FIELD_2'):<?=$FORM->ShowInput('REQ_FIELD_2')?><br />
Копировать
```

#### Смотрите также

- [Класс CFormOutput](/api_help/form/classes/cformoutput/index.php)
- [CFormOutput::ShowInput](/api_help/form/classes/cformoutput/showinput.php)
- [CFormOutput::ShowInputCaption](/api_help/form/classes/cformoutput/showinputcaption.php)

Новинки документации в соцсетях: