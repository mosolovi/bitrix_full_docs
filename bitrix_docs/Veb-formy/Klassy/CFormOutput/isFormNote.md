[Веб-формы](/api_help/form/index.php)

[Классы](/api_help/form/classes/index.php)

[CFormOutput](/api_help/form/classes/cformoutput/index.php)

isFormNote (5.1.1)

isFormNote
==========

```
bool
CFormOutput::isFormNote(
);Копировать
```

Проверка условия "есть ли текстовые заметки". Метод нестатический.

#### Параметры метода

Нет параметров.

#### Возвращаемое значение

*true*, если у есть текстовые заметки. *false* в противном
случае.

#### Примеры использования

```
<?if($FORM->isFormNote()):?>Ответ: <?=$FORM->ShowFormNote()?><?endif?>
Копировать
```

```
\\ способ проверить, отправлена ли форма, а затем вывести сообщение об успешной отправке
<? if($FORM->isFormNote()) //т.е. если сообщение есть, значит нужно его показать, т.е. форма отправлена
{
	echo $FORM->ShowFormNote();?> //выводим сообщение "Ваша заявка успешно отправлена"
}
else //в противном случает выводим саму форму для заполнения
{
	шаблон формы
}
?>
Копировать
```

#### Смотрите также

[Класс CFormOutput](/api_help/form/classes/cformoutput/index.php)  
[CFormOutput::ShowFormNote](/api_help/form/classes/cformoutput/showformnote.php)

Новинки документации в соцсетях: