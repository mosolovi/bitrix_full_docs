[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormOutput](/api_help/form/classes/cformoutput/index.php)

ShowResetButton (5.1.1)

ShowResetButton
===============

```
string
CFormOutput::ShowResetButton([
	string CAPTION = "",
	string CSSClass = ""
]
);Копировать
```

Возвращает HTML-код кнопки "Сбросить" формы создания/редактирования записи. Метод нестатический.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| *CAPTION* | Текст, расположенный на кнопке. Если параметр пуст или не указан, то будет использовано значение по умолчанию. Необязательный параметр. | 5.1.2 |
| *CSSClass* | CSS-класс кнопки. Необязательный параметр. | 5.1.2 |

#### Возвращаемое значение

Возвращается HTML-код кнопки "сбросить".

#### Использование

```
<?=$FORM->ShowResetButton("Отменить изменения", "form-button-reset")?>
Копировать
```

#### Смотрите также

- [Класс CFormOutput](/api_help/form/classes/cformoutput/index.php)
- [CFormOutput::ShowApplyButton](/api_help/form/classes/cformoutput/showapplybutton.php)
- [CFormOutput::ShowSubmitButton](/api_help/form/classes/cformoutput/showsubmitbutton.php)

Новинки документации в соцсетях: