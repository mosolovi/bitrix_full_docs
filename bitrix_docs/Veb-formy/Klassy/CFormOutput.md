[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormOutput](/api_help/form/classes/cformoutput/index.php)

Класс CFormOutput (5.1.1)

Класс CFormOutput
=================

Включить вкладки

Описание и методы

Примеры

### Описание и методы

**CFormOutput** - класс для работы с шаблонами форм

#### Использование класса

Класс используется для для управления визульным отображением формы. При
выводе шаблона формы, ему передается переменная `$FORM` -
инициализированный экземпляр класса. Шаблон формируется в виде HTML-кода со
вставками вызовов методов класса (пример [см. ниже](#form_ex)).
Возможно визуальное редактирование шаблона, а также, создание формы на основе
шаблона.

#### Основные методы класса

Основные методы класса.

| Метод | Описание | С версии |
| --- | --- | --- |
| [ShowApplyButton](/api_help/form/classes/cformoutput/showapplybutton.php) | Вывод кнопки "Применить". |  |
| [ShowCaptcha](/api_help/form/classes/cformoutput/showcaptcha.php) | Вывод отформатированных полей ввода CAPTCHA. |  |
| [ShowCaptchaField](/api_help/form/classes/cformoutput/showcaptchafield.php) | Вывод поля для ввода текста CAPTCHA. |  |
| [ShowCaptchaImage](/api_help/form/classes/cformoutput/showcaptchaimage.php) | Вывод изображения CAPTCHA. |  |
| [ShowErrorMsg](/api_help/form/classes/cformoutput/showerrormsg.php) | Вывод ошибок модуля формы. Вызывается автоматически. |  |
| [ShowFormDescription](/api_help/form/classes/cformoutput/showformdescription.php) | Вывод описания формы. |  |
| [ShowFormErrors](/api_help/form/classes/cformoutput/showformerrors.php) | Вывод отформатированного списка ошибок валидатора формы. |  |
| [ShowFormErrorsText](/api_help/form/classes/cformoutput/showformerrorstext.php) | Вывод неотформатированного списка ошибок валидатора формы. |  |
| [ShowFormFooter](/api_help/form/classes/cformoutput/showformfooter.php) | Вывод завершающей части HTML-кода формы. Вставляется в конец шаблона автоматически. |  |
| [ShowFormHeader](/api_help/form/classes/cformoutput/showformheader.php) | Вывод заголовка HTML-кода формы. Вставляется в начало шаблона автоматически. |  |
| [ShowFormImage](/api_help/form/classes/cformoutput/showformimage.php) | Вывод картинки формы. |  |
| [ShowFormNote](/api_help/form/classes/cformoutput/showformnote.php) | Вывод отформатированных заметок формы. |  |
| [ShowFormNoteText](/api_help/form/classes/cformoutput/showformnotetext.php) | Вывод неотформатированных заметок формы. |  |
| [ShowFormTitle](/api_help/form/classes/cformoutput/showformtitle.php) | Вывод текстового заголовка формы. |  |
| [ShowInput](/api_help/form/classes/cformoutput/showinput.php) | Вывод поля формы. |  |
| [ShowInputCaption](/api_help/form/classes/cformoutput/showinputcaption.php) | Вывод подписи поля формы. |  |
| [ShowInputCaptionImage](/api_help/form/classes/cformoutput/showinputcaptionimage.php) | Вывод картинки поля формы. |  |
| [ShowRequired](/api_help/form/classes/cformoutput/showrequired.php) | Вывод метки "обязательное поле". |  |
| [ShowResetButton](/api_help/form/classes/cformoutput/showresetbutton.php) | Вывод кнопки "Сбросить". |  |
| [ShowSubmitButton](/api_help/form/classes/cformoutput/showsubmitbutton.php) | Вывод кнопки отправки формы. |  |
| [SetInputDefaultValue](/api_help/form/classes/cformoutput/setinputdfefaultvalue.php) | Устанавливает значение *по умолчанию* для поля веб-формы. | 5.9.2 |

Методы для проверки условий. Все условные методы недоступны в режиме
визуального редактора. Их можно использовать только в режиме редактирования
PHP-кода.

| Метод | Описание | С версии |
| --- | --- | --- |
| [isFormDescription](/api_help/form/classes/cformoutput/isformdescription.php) | Имеет ли форма описание. |  |
| [isFormErrors](/api_help/form/classes/cformoutput/isformerrors.php) | Есть ли ошибки валидатора. |  |
| [isFormImage](/api_help/form/classes/cformoutput/isformimage.php) | Имеет ли форма картинку. |  |
| [isFormNote](/api_help/form/classes/cformoutput/isformnote.php) | Имеет ли форма заметки. |  |
| [isFormTitle](/api_help/form/classes/cformoutput/isformtitle.php) | Имеет ли форма текстовый заголовок. |  |
| [isInputCaptionImage](/api_help/form/classes/cformoutput/isinputcaptionimage.php) | Имеет ли поле формы картинку. |  |
| [isUseCaptcha](/api_help/form/classes/cformoutput/isusecaptcha.php) | Используется ли в форме CAPTCHA. |  |

### Примеры

#### Пример шаблона формы

`$FORM` - экземпляр класса `CFormOutput` -
создаётся и инициализируется автоматически вне шаблона. Вызов методов
`CFormOutput::ShowFormHeader()` и
`CFormOutput::ShowFormFooter()` также добавляется к шаблону
автоматически.

```
 <!-- Выведем описание формы -->
<table width="100%" cellpadding="2" cellspacing="0" border="0">
	<tr>
		<td align="center"><?=$FORM->ShowFormDescription()?></td>
	</tr>
</table>
<!-- Если есть ошибки валидатора - выведем их -->
<?if($FORM->isFormErrors()):?>
<table width="100%" cellpadding="2" cellspacing="0" border="0">
	<tr>
		<td><?=$FORM->ShowFormErrors()?></td>
	</tr>
</table>
<?endif?>
<!-- Выведем поля формы -->
<table width="100%" cellpadding="2" cellspacing="0" border="0">
	<tr>
		<td width="40%" valign="top" align="right"><?=$FORM->ShowInputCaption('test_q')?>: </td>
		<td width="60%" valign="top"><?=$FORM->ShowInput('test_q')?></td>
	</tr>
	<tr>
		<td valign="top" align="right"><?=$FORM->ShowInputCaption('test_q_text')?>: </td>
		<td valign="top"><?=$FORM->ShowInput('test_q_text')?></td>
	</tr>
	<tr>
		<td valign="top" align="right"><?=$FORM->ShowInputCaption('test_q_textarea')?>: </td>
		<td valign="top"><?=$FORM->ShowInput('test_q_textarea')?></td>
	</tr>
</table>
<!-- Если используется CAPTCHA - выведем картинку и поле для ввода -->
<?if($FORM->isUseCaptcha()):?>
<table width="100%" cellpadding="2" cellspacing="0" border="0">
	<tr>
		<td colspan="2" height="8"></td>
	</tr>
	<tr>
		<td width="40%" valign="top" align="right" class="text">Защита от автоматической регистрации: </td>
		<td width="60%" valign="top"><?=$FORM->ShowCaptchaImage()?></td>
	</tr>
	<tr>
		<td valign="top" align="right" class="text">Введите слово с картинки<?=$FORM->ShowRequired()?>: </td>
		<td valign="top"><?=$FORM->ShowCaptchaField()?></td>
	</tr>
</table>
<?endif?>
<!-- Выведем кнопки формы -->
<table width="100%" cellpadding="2" cellspacing="0" border="0">
	<tr>
		<td width="40%">&nbsp;</td>
		<td width="60%">
			<?=$FORM->ShowSubmitButton()?>&nbsp;
			<?=$FORM->ShowApplyButton()?>&nbsp;
			<?=$FORM->ShowResetButton()?>
		</td>
	</tr>
</table>Копировать
```

Если не предполагается использование страниц редактирования результата формы
или просмотра списка результатов, то имеет смысл вставить в шаблон ответ
веб-формы в обход основного шаблона:

```
 <!-- Если есть ответ формы - выведем его в обход шаблона -->
<?if($FORM->isFormNote()):?>
<?=$FORM->ShowFormNote()?>
<?else:?>
<!-- здесь остальной шаблон веб-формы -->
<?endif?>Копировать
```

Новинки документации в соцсетях: