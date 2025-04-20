[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormOutput](/api_help/form/classes/cformoutput/index.php)

isUseCaptcha (5.1.1)

isUseCaptcha
============

```
bool
CFormOutput::isUseCaptcha(
);Копировать
```

Проверка условия "форма использует CAPTCHA". Метод нестатический.

#### Параметры метода

Нет параметров.

#### Возвращаемое значение

*true*, если форма использует CAPTCHA. *false* в противном
случае.

#### Использование

```
<?if($FORM->isUseCaptcha()):?>
<tr>
	<td colspan="2" height="8"></td>
</tr>
<tr>
	<td valign="top" align="right" class="text">Защита от автоматической регистрации:</td>
	<td valign="top"><?=$FORM->ShowCaptchaImage()?></td>
</tr>
<tr>
	<td valign="top" align="right" class="text">Введите слово с картинки<?=$FORM->ShowRequired()?>:</td>
	<td valign="top"><?=$FORM->ShowCaptchaField()?></td>
</tr>
<?endif?>Копировать
```

#### Смотрите также

- [Класс CFormOutput](/api_help/form/classes/cformoutput/index.php)
- [CFormOutput::ShowCaptcha](/api_help/form/classes/cformoutput/showcaptcha.php)
- [CFormOutput::ShowCaptchaField](/api_help/form/classes/cformoutput/showcaptchafield.php)
- [CFormOutput::ShowCaptchaImage](/api_help/form/classes/cformoutput/showcaptchaimage.php)

Новинки документации в соцсетях: