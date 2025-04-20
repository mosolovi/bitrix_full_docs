[JS библиотека](/api_help/js_lib/index.php)

[AJAX расширение](/api_help/js_lib/ajax/index.php)

BX.ajax.runComponentAction (с версии 20.5.462)

BX.ajax.runComponentAction
==========================

```
BX.ajax.runComponentAction(component, action[, config])Копировать
```

BX.ajax.runComponentAction - это метод для запуска аякс-действий в компоненте, который возвращает BX.Promise. Если был просрочен csrf-токен, то он сам попробует его восстановить (выполняется только одна попытка) и повторить запрос. Если от сервера пришёл ответ, в котором **status** не равен `success`, то promis'y выполняется reject.

#### Параметры

| Параметр | Описание | С версии |
| --- | --- | --- |
| component {string} | Полное имя компонента, куда шлём запрос. Например, bitrix:main.post.form или vendor:example. |  |
| action {string} | Действие, которое необходимо запустить. Например, greet. |  |
| config {Object} | Параметры:  * **mode {string}** Допустимое значение либо class, либо ajax:     class - запуск действия внутри class.php,    ajax - запуск действия внутри ajax.php * **data {Object|FormData}** Объект с данными, которые будут посланы в теле запроса. Как в [BX.ajax](/api_help/js_lib/ajax/bx_ajax.php). * **json {Object}** - объект с данными, которые будут переданы в теле запроса. При этом при отправке будет проставлен `contentType: application/json`, а контроллеры смогут получить доступ к оригинальному JSON'y, что позволит удобнее работать с числами и пустыми значениями. * **navigation {Object}** - объект постраничной навигации.   + **page {number}** - номер страницы. Отсчет начинается с 1. * **signedParameters {string}** Необязательный. Это строка с подписанными параметрами. Генерируется методом getSignedParameters() * **analyticsLabel {string|Object}** Необязательный параметр используется, как пометка хитов для аналитики. * **method {string}** Необязательный. По умолчанию, POST. |  |

Если ответ не будет содержать ключи **data** и **status**, запрос будет обрабатываться с ошибкой Network Error.

#### Пример

Представим, мы делаем аякс-запрос на компонент vendor:example из примера. И вызываем там действие greet.

```
BX.ajax.runComponentAction('vendor:example', 'greet', {
	mode: 'class', //это означает, что мы хотим вызывать действие из class.php
	data: {
		person: 'Hero!' //данные будут автоматически замаплены на параметры метода 
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
		"data": "Hi Hero!", 
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

#### Дополнительно

* [Контроллеры](https://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&CHAPTER_ID=03750) в курсе "Разработчик Bitrix Framework".

Новинки документации в соцсетях: