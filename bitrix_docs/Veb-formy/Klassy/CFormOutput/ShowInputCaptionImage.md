[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormOutput](/api_help/form/classes/cformoutput/index.php)

ShowInputCaptionImage (5.1.1)

ShowInputCaptionImage
=====================

Включить вкладки

Описание и параметры

Использование

Смотрите также

### Описание и параметры

```
string
CFormOutput::ShowInputCaptionImage(
	string $FIELD_SID[,
	string $sAlign = "", 
	int $iMaxW = 0
	int $iMaxH = 0
	string $bPopup = "N", 
	string $strPopupTitle = "", 
	string $sHSpace = "", 
	string $sVSpace = "", 
	string $sBorder = ""
]
);Копировать
```

Вывод изображения, прикрепленного к вопросу формы. Если изображение есть, возвращается HTML-код вставки. В противном случае - пустая строка. Метод нестатический.

#### Параметры метода

Параметры метода идентичны параметрам CFile::ShowImage

| Параметр | Описание | С версии |
| --- | --- | --- |
| *FIELD\_SID* | Строковой идентификатор поля вопроса. Обязательный параметр. |  |
| *sAlign* | Расположение изображения относительно текста. Может принимать одно из четырех значений - `LEFT`, `CENTER`, `RIGHT` (регистр не имеет значения) или пустое. Необязательный параметр. | 5.1.2 |
| *iMaxW* | Максимальная ширина изображения. Если ширина картинки больше iMaxW, то она будет пропорционально смаштабирована.  Необязательный. До версии 5.1.2 значение по умолчанию - "0" - без ограничений. |  |
| *iMaxH* | Максимальная высота изображения. Если высота картинки больше iMaxH, то она будет пропорционально смаштабирована.  Необязательный. До версии 5.1.2 значение по умолчанию - "0" - без ограничений. |  |
| *bPopup* | Открывать ли при клике на изображении дополнительное popup окно с увеличенным изображением.  Необязательный. Должен приниметь одно из двух значений - "Y" или "N" (с учётом регистра). По умолчанию - "N" (до версии 5.1.2 - "false"). |  |
| *strPopupTitle* | Текст всплывающей подсказки на изображении (только если *bPopup* = "Y")  Необязательный. По умолчанию выводится фраза "Нажмите чтобы увеличить" на языке страницы (до версии 5.1.2 - "false"). |  |
| *sHSpace* | Устанавливает вертикальный отступ картинки от окружающего текста в пикселях.  Необязательный. По умолчанию - "0" - без отступа. | 5.1.2 |
| *sVSpace* | Устанавливает горизонтальный отступ картинки от окружающего текста в пикселях.  Необязательный. По умолчанию - "0" - без отступа. | 5.1.2 |
| *sBorder* | Устанавливает толщину рамки вокруг изображения. Необязательный. По умолчанию равен "0" - без рамки: | 5.1.2 |

#### Возвращаемое значение

Возвращает HTML-код для вставки изображения в форму

### Использование

```
<?=$FORM->ShowInputCaptionImage('MYFIELD_5', 'LEFT', 50, 50, "N", "", 5, 5)?>
Копировать
```

### Смотрите также

- [Класс CFormOutput](/api_help/form/classes/cformoutput/index.php)
- [CFile::ShowImage](/api_help/main/reference/cfile/showimage.php)
- [CFormOutput::ShowInput](/api_help/form/classes/cformoutput/showinput.php)
- [CFormOutput::ShowInputCaption](/api_help/form/classes/cformoutput/showinputcaption.php)
- [CFormOutput::isInputCaptionImage](/api_help/form/classes/cformoutput/isinputcaptionimage.php)

Новинки документации в соцсетях: