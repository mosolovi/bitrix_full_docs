[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormOutput](/api_help/form/classes/cformoutput/index.php)

ShowInputCaption (5.1.1)

ShowInputCaption
================

```
string
CFormOutput::ShowInputCaption(
	string $FIELD_SID[, 
	string $CSSClass = ""]
);Копировать
```

Вставка в шаблон подписи поля ответа на вопрос. Метод нестатический.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *FIELD\_SID* | Строковой идентификатор поля вопроса. Обязательный параметр. |
| *CSSClass* | CSS-класс подписи. Необязательный параметр. Если для выставлено значение "Текст вопроса - HTML", то параметр игнорируется. До версии 5.1.2 значение по умолчанию - "tablebodytext". |

#### Возвращаемое значение

Возвращается обработанная подпись поля формы.

#### Использование

```
<?=$FORM->ShowInputCaption('MYFIELD_5')?>
Копировать
```

#### Смотрите также

- [Класс CFormOutput](/api_help/form/classes/cformoutput/index.php)
- [CFormOutput::ShowInput](/api_help/form/classes/cformoutput/showinput.php)
- [CFormOutput::ShowInputCaptionImage](/api_help/form/classes/cformoutput/showinputcaptionimage.php)

Новинки документации в соцсетях: