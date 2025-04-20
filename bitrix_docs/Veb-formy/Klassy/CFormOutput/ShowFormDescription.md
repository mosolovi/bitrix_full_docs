[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormOutput](/api_help/form/classes/cformoutput/index.php)

ShowFormDescription (5.1.1)

ShowFormDescription
===================

```
string
CFormOutput::ShowFormDescription([
	string CSSClass = ""
]
);Копировать
```

Вывод описательного текста формы. Метод нестатический.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| *CSSClass* | CSS-класс который нужно применить к выводимому тексту. Необязательный параметр. Если для описания формы выставлено значение "HTML", то параметр игнорируется. | 5.1.2 |

#### Возвращаемое значение

Возвращает описательный текст формы

#### Использование

```
<?=$FORM->ShowFormDescription("form-description-text")?>
Копировать
```

#### Смотрите также

- [Класс CFormOutput](/api_help/form/classes/cformoutput/index.php)
- [CFormOutput::ShowFormTitle](/api_help/form/classes/cformoutput/showformtitle.php)
- [CFormOutput::ShowFormImage](/api_help/form/classes/cformoutput/showformimage.php)
- [CFormOutput::isFormDescription](/api_help/form/classes/cformoutput/isformdescription.php)

Новинки документации в соцсетях: