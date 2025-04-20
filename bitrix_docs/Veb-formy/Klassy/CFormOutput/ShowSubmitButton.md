[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormOutput](/api_help/form/classes/cformoutput/index.php)

ShowSubmitButton (5.1.1)

ShowSubmitButton
================

```
string
CFormOutput::ShowSubmitButton([
	string CAPTION = "",
	string CSSClass = ""
]
);Копировать
```

Возвращает HTML-код кнопки отправки формы создания/редактирования записи. Метод нестатический.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| *CAPTION* | Текст, расположенный на кнопке. Если параметр пуст или не указан, то будет использовано значение параметра "Подпись на кнопке" вкладки "Свойства" страницы редактирования параметров веб-формы, либо значение по умолчанию. Необязательный параметр. | 5.1.2 |
| *CSSClass* | CSS-класс кнопки. Необязательный параметр. | 5.1.2 |

#### Возвращаемое значение

Возвращается HTML-код кнопки отправки формы

#### Использование

```
<?=$FORM->ShowSubmitButton("Отправить заявку", "form-button-submit")?>
Копировать
```

#### Смотрите также

- [Класс CFormOutput](/api_help/form/classes/cformoutput/index.php)
- [CFormOutput::ShowApplyButton](/api_help/form/classes/cformoutput/showapplybutton.php)
- [CFormOutput::ShowResetButton](/api_help/form/classes/cformoutput/showresetbutton.php)

Новинки документации в соцсетях: