[JS библиотека](/api_help/js_lib/index.php)

[AJAX расширение](/api_help/js_lib/ajax/index.php)

BX.ajax.runAction (с версии 20.5.462)

BX.ajax.runAction
=================

```
BX.ajax.runAction(action[, config])Копировать
```

BX.ajax.runAction - это метод для запуска аякс-действий в модуле, который возвращает BX.Promise. Если был просрочен csrf-токен, то он сам попробует его восстановить (выполняется только одна попытка) и повторить запрос. Если от сервера пришёл ответ, в котором **status** не равен `success`, то promis'y выполняется reject.

#### Параметры

| Параметр | Описание | С версии |
| --- | --- | --- |
| action {string} | Действие, которое необходимо запустить. Например, *disk.folder.get*. |  |
| config {Object} | Параметры:  * **data {Object|FormData}** - объект с данными, которые будут посланы в теле запроса. Аналогично [BX.ajax](/api_help/js_lib/ajax/bx_ajax.php). * **json {Object}** - объект с данными, которые будут переданы в теле запроса. При этом при отправке будет проставлен `contentType: application/json`, а контроллеры смогут получить доступ к оригинальному JSON'y, что позволит удобнее работать с числами и пустыми значениями. * **navigation {Object}** - объект постраничной навигации.   + **page {number}** - номер страницы. Отсчет начинается с 1.   + **size {number}** - размер страницы (от 1 до 50). По умолчанию 20. * **analyticsLabel {string|Object}** - необязательный параметр используется, как пометка хитов для аналитики. * **method {string}** - необязательный. По умолчанию, POST. |  |

#### Пример

```
BX.ajax.runAction('disk.folder.get', {
	data: {
		folderId: 1 
	},
	analyticsLabel: {
		viewMode: 'grid',
		filterState: 'closed'	
	}
}).then(function (response) {
	console.log(response);
	/**
	{
		"status": "success", 
		"data": {
			"ID": 1,
			...
		}, 
		"errors": []
	}
	**/			
}, function (response) {
	//сюда будут приходить все ответы, у которых status !== 'success'
	console.log(response);
	/**
	{
		"status": "error", 
		"errors": [...]
	}
	**/				
});Копировать
```

Новинки документации в соцсетях: