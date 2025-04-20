[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormOutput](/api_help/form/classes/cformoutput/index.php)

ShowApplyButton (5.1.1)

ShowApplyButton
===============

```
string
CFormOutput::ShowApplyButton([
	string CAPTION = "",
	string CSSClass = ""
]
);Копировать
```

Возвращает HTML-код кнопки "Применить" формы создания/редактирования записи. Метод нестатический.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| *CAPTION* | Текст, расположенный на кнопке. Необязательный параметр. Параметр необязательный, и если он пуст или не указан, то будет использовано значение по умолчанию. | 5.1.2 |
| *CSSClass* | CSS-класс кнопки. Необязательный параметр. | 5.1.2 |

#### Возвращаемое значение

Возвращается HTML-код кнопки "Применить"

#### Использование

```
<?=$FORM->ShowApplyButton("Применить", "form-button-apply")?>
Копировать
```

#### Смотрите также

- [Класс CFormOutput](/api_help/form/classes/cformoutput/index.php)
- [CFormOutput::ShowResetButton](/api_help/form/classes/cformoutput/showresetbutton.php)
- [CFormOutput::ShowSubmitButton](/api_help/form/classes/cformoutput/showsubmitbutton.php)

Новинки документации в соцсетях: