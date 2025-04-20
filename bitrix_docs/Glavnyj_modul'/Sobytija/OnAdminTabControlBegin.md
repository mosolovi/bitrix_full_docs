[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnAdminTabControlBegin (с версии 9.5.10)

OnAdminTabControlBegin
======================

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
void
Handler(
	&form
);Копировать
```

Событие OnAdminTabControlBegin вызывается в функции [CAdminTabControl::Begin()](/api_help/main/general/admin.section/classes/cadmintabcontrol/begin.php) при выводе в административном интерфейсе формы редактирования. Событие позволяет изменить или добавить собственные вкладки формы редактирования.

#### Параметры функции

| Параметр | Описание |
| --- | --- |
| form | Ссылка на объект класса [CAdminTabControl](/api_help/main/general/admin.section/classes/cadmintabcontrol/index.php). Использование члена класса $form->tabs позволяет получить доступ к закладкам формы. Структура массива закладок описана на странице [Конструктор CAdminTabControl](/api_help/main/general/admin.section/classes/cadmintabcontrol/cadmintabcontrol.php). |

#### Возвращаемое значение

Возвращаемое значение не используется.

#### Смотрите также

* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)
* [Создание формы редактирования](/api_help/main/general/admin.section/rubric_edit.php)

### Примеры использования

```
<?
AddEventHandler("main", "OnAdminTabControlBegin", "MyOnAdminTabControlBegin");
public static function MyOnAdminTabControlBegin(&$form)
{
	if($GLOBALS["APPLICATION"]->GetCurPage() == "/bitrix/admin/posting_edit.php")
	{
		$form->tabs[] = array("DIV" => "my_edit", "TAB" => "Дополнительно", "ICON"=>"main_user_edit", "TITLE"=>"Дополнительные параметры", "CONTENT"=>
			'<tr valign="top">
				<td>Дополнительные заголовки письма:</td>
				<td>
					<input type="text" name="MY_HEADERS[]" value="" size="30"><br>
					<input type="text" name="MY_HEADERS[]" value="" size="30"><br>
					<input type="text" name="MY_HEADERS[]" value="" size="30"><br>
				</td>
			</tr>'
		);
	}
}
?>Копировать
```

Новинки документации в соцсетях: