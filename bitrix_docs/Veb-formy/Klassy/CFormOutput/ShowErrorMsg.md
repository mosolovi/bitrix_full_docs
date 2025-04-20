[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormOutput](/api_help/form/classes/cformoutput/index.php)

ShowErrorMsg (5.1.1)

ShowErrorMsg
============

```
string
CFormOutput::ShowErrorMsg(
);Копировать
```

Возвращает код ошибки инициализации формы. Метод нестатический.

#### Параметры метода

Нет параметров.

#### Возвращаемое значение

Метод возвращает одну из следующих строк, либо пустую строку, если ошибок нет

| Строка | Описание |
| --- | --- |
| FORM\_NOT\_FOUND | Формы с переданным WEB\_FORM\_ID не существует |
| FORM\_ACCESS\_DENIED | Не хватает прав доступа к форме |

Проверка наличия ошибки и вывод соответствующего ей языкового сообщения производится автоматически при инициализации формы

#### Смотрите также

- [Класс CFormOutput](/api_help/form/classes/cformoutput/index.php)
- [CFormOutput::ShowFormErrors](/api_help/form/classes/cformoutput/showformerrors.php)
- [CFormOutput::ShowFormErrorsText](/api_help/form/classes/cformoutput/showformerrorstext.php)

Новинки документации в соцсетях: