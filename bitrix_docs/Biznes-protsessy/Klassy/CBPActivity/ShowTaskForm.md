[Бизнес-процессы](/api_help/bizproc/index.php)

[Классы](/api_help/bizproc/bizproc_classes/index.php)

[CBPActivity](/api_help/bizproc/bizproc_classes/CBPActivity/index.php)

ShowTaskForm

ShowTaskForm
============

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
return CBPActivity::CallStaticMethod(
	$arTask["ACTIVITY"],
	"ShowTaskForm",
	array(
		$arTask,
		$userId,
		$userName,
		$arRequest
	)
)Копировать
```

Метод возвращает массив из двух элементов: первый - часть HTML формы (поле для комментария, поля ввода доп.информации), второй - HTML кнопки формы (Ознакомлен, Утвердить и т.п.)

Метод принимает массив конфигурационных параметров и генерирует скрипты, необходимые для показа файлового диалога. Метод статический.

**Внимание!** Метод устарел и больше не используется.

#### Параметры метода

| Параметр | Описание |
| --- | --- |
| *$arTask* | Массив с параметрами задания. |
| *$userId* | Пользователь, который запрашивает форму задания. |
| *$userName* | Имя пользователя. |
| *$arRequest* | Данные из наполнения формы (например, когда пользователь заполнил форму, но она не прошла валидацию - те данные, что он ввел ранее, передаются, чтобы при перезагрузке страницы введенная информация не потерялась). |

### Примеры использования

```
return array(
	'<tr><td valign="top" width="40%" align="right" class="bizproc-field-name">'.(strlen($arTask["PARAMETERS"]["CommentLabelMessage"]) > 0 ? 
	$arTask["PARAMETERS"]["CommentLabelMessage"] : GetMessage("BPAA_ACT_COMMENT")).':</td>'.
	'<td valign="top" width="60%" class="bizproc-field-value">'.
	'<textarea rows="3" cols="50" name="task_comment"></textarea>'.
	'</td></tr>',
	'<input type="submit" name="approve" value="'.(strlen($arTask["PARAMETERS"]["TaskButton1Message"]) > 0 ? 
	$arTask["PARAMETERS"]["TaskButton1Message"] : GetMessage("BPAA_ACT_BUTTON1")).'"/>'.
	'<input type="submit" name="nonapprove" value="'.(strlen($arTask["PARAMETERS"]["TaskButton2Message"]) > 0 ? 
	$arTask["PARAMETERS"]["TaskButton2Message"] : GetMessage("BPAA_ACT_BUTTON2")).'"/>'
);
Копировать
```

Новинки документации в соцсетях: