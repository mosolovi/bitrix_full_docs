[JS библиотека](/api_help/js_lib/index.php)

[Административная оконная библиотека](/api_help/js_lib/window/index.php)

[BX.CDialog](/api_help/js_lib/window/cdialog/index.php)

new BX.CDialog

new BX.CDialog
==============

```
new BX.CDialog(
	params
);Копировать
```

Конструктор.

#### Параметры функции

```
{
	(
		title: 'dialog title',
		head: 'head block html',
		content: 'dialog content',
		icon: 'head icon classname or filename'
	)
	или
	(
		content_url: url to content load
			loaded content scripts can use BX.WindowManager.Get() to get access to the current window object
	)
		
	height: window_height_in_pixels,
	width: window_width_in_pixels,
		
	draggable: true|false,
	resizable: true|false,
		
	min_height: min_window_height_in_pixels, // useless if resizable = false
	min_width: min_window_width_in_pixels, // useless if resizable = false
		
	buttons: [
		'html_code',
		BX.CDialog.prototype.btnSave, BX.CDialog.prototype.btnCancel, BX.CDialog.prototype.btnClose,
		{
			title: заголовок кнопки,
			name: имя кнопки,
			id: id кнопки,
			action: function () {
				this.Close();
			},
			onclick: "BX.WindowManager.Get().Close()"
		},
		new CWindowButton({
			title: заголовок кнопки,
			name: имя кнопки,
			id: id кнопки,
			action: function () {
				this.Close();
			},
			onclick: "BX.WindowManager.Get().Close()"
		})
	]
}Копировать
```

| Параметр | Описание |
| --- | --- |
| title | Название диалога |
| head | html код заголовка |
| content | Контент диалога |
| content\_url | URL для загрузки контента. Загружаемые скрипты могут использовать **BX.WindowManager.Get** для получения доступа к объекту текущего окна. Параметр может использоваться вместо первых трёх. |
| content\_post | POST-данные, которые нужно передать для формирования контента. Необязательный параметр. |
| height | Высота диалога в пикселях |
| width | Ширина диалога в пикселях |
| draggable | (true|false) Разрешение на использование drag&drop |
| resizable | (true|false) Разрешение на изменение размеров окна |
| min\_height | Минимальная высота диалога в пикселях. *false* - при запрете на изменение размера. |
| min\_width | Минимальная ширина диалога в пикселях. *false* - при запрете на изменение размера. |
| buttons | Массив, элементами которого являются описания кнопок. Описание каждой кнопки может быть HTML-кодом кнопки, может быть экземпляром класса **BX.CWindowButton** или объектом со следующими параметрами:.  ``` { 	title - заголовок кнопки,  	name - имя кнопки,  	id - id кнопки,  	action - обработчик нажатия на кнопку }Копировать ```  Кроме того, есть стандартные кнопки:  * BX.CDialog.prototype.btnSave - кнопка **Сохранить** * BX.CDialog.prototype.btnCancel - кнопка **Отменить** * BX.CDialog.prototype.btnClose - Кнопка **Закрыть** |

Новинки документации в соцсетях: