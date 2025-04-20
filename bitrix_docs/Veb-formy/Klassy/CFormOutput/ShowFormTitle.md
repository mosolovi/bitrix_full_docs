[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormOutput](/api_help/form/classes/cformoutput/index.php)

ShowFormTitle (5.1.1)

ShowFormTitle
=============

```
string
CFormOutput::ShowFormTitle([
	string CSSClass = ""
]
);Копировать
```

Вывод текстового заголовка формы. Метод нестатический.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| *CSSClass* | CSS-класс который нужно применить к выводимому тексту. Необязательный параметр. | 5.1.2 |

#### Возвращаемое значение

Возвращает текстовый заголовок (название) формы

#### Использование

```
<?=$FORM->ShowFormTitle("form-title")?>
Копировать
```

#### Смотрите также

- [Класс CFormOutput](/api_help/form/classes/cformoutput/index.php)
- [CFormOutput::ShowFormDescription](/api_help/form/classes/cformoutput/showformdescription.php)
- [CFormOutput::ShowFormImage](/api_help/form/classes/cformoutput/showformimage.php)
- [CFormOutput::isFormTitle](/api_help/form/classes/cformoutput/isformtitle.php)

Новинки документации в соцсетях: