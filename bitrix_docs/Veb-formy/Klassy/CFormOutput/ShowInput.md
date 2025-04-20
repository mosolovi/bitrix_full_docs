[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormOutput](/api_help/form/classes/cformoutput/index.php)

ShowInput (5.1.1)

ShowInput
=========

```
string
CFormOutput::ShowInput(
	string $FIELD_SID[, 
	string $CSSClass = ""]
);Копировать
```

Вставка полей ответа на вопрос в шаблон. Параметры поля ввода задаются в настройках вопроса. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *FIELD\_SID* | Строковой идентификатор поля вопроса. Обязательный параметр. |
| *CSSClass* | CSS-класс для подписи к полю ввода. Необязательный параметр. |

#### Возвращаемое значение

Возвращается HTML-код для вставки полей формы

#### Использование

```
<?=$FORM->ShowInput('MYFIELD_5')?>
Копировать
```

#### Смотрите также

- [Класс CFormOutput](/api_help/form/classes/cformoutput/index.php)
- [CFormOutput::ShowInputCaption](/api_help/form/classes/cformoutput/showinputcaption.php)
- [CFormOutput::ShowInputCaptionImage](/api_help/form/classes/cformoutput/showinputcaptionimage.php)

Новинки документации в соцсетях: