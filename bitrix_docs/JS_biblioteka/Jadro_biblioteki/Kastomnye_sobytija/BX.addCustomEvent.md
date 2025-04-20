[JS библиотека](/api_help/js_lib/index.php)

[Ядро библиотеки](/api_help/js_lib/kernel/index.php)

[Кастомные события](/api_help/js_lib/kernel/castom_events/index.php)

BX.addCustomEvent

BX.addCustomEvent
=================

Включить вкладки

Описание

Получение списка всех событий в системе

Примеры использования

### Описание

#### Функция BX.addCustomEvent

Функция подразумевает два варианта входных параметров.

```
void 
BX.addCustomEvent(
	Object eventObject,
	string eventName,
	Function eventHandler
);Копировать
```

```
void 
BX.addCustomEvent(
	string eventName,
	Function eventHandler
);Копировать
```

Функция назначает обработчик **eventHandler** кастомному событию с именем **eventName**, возникающем в объекте **eventObject**. Если **eventObject** не указан (короткий вызов), то обработчик будет вызываться при каждом вызове события с таким именем в любом объекте.

### Получение списка всех событий в системе

При работе с кастомными событиями возникает резонный вопрос - как получить полный список событий, который присутствует в системе (актуально для готовых шаблонов, административной части, и Битрикс24-коробки) ?

Данную задачу можно решить следующим образом - в файле `/bitrix/js/main/core/core.js` находим:

```
BX.onCustomEvent(eventObject, eventName, arEventParams, secureParams);
Копировать
```

Вставим в его исполнение логирование:

```
console.log(eventName, arEventParams);Копировать
```

После этого при совершении различных действий на клиенте (клики, push-информации, открытии popup) в лог будут писаться коды событий. Вам останется подобрать нужное.

**Примечание**: не забудьте удалить в ядре строчку логирования после сбора необходимой информации.

### Примеры использования

**Как добавить свои шрифты в визуальный редактор**

На событии GetFontFamilyList добавить нужные шрифты в массив. Тогда они начнут выводиться в списке шрифтов в редакторе.

```
BX.addCustomEvent('GetFontFamilyList', BX.delegate(function (fontlist) {
	fontlist.push({value: 'RobotoThin', name: 'RobotoThin'});
	fontlist.push({value: 'RobotoLight', name: 'RobotoLight'});
	fontlist.push({value: 'RobotoRegular', name: 'RobotoRegular'});
	fontlist.push({value: 'RobotoBlack', name: 'RobotoBlack'});
	for(var key in userFonts) {
		fontList.push({value: userFonts[key], name: userFonts[key]})
	}
}));Копировать
```

**Как зафиксировать обновление счетчика**

Для этого нужно добавить обработчик события:

```
BX.addCustomEvent("onPullEvent-main", BX.delegate(function(command,params){
	if (command == 'user_counter' && params[BX.message('SITE_ID')] && params[BX.message('SITE_ID')]['__НАЗВАНИЕ_ВАШЕГО_СЧЕТЧИКА__'])
	{
		// вызвать код для обновления счетчика
		// в params[BX.message('SITE_ID')]['__НАЗВАНИЕ_ВАШЕГО_СЧЕТЧИКА__'] будет новое значение счетчика
	}
}, this));Копировать
```

Для мобильной версии:

```
BX.addCustomEvent("onPull-main", BX.delegate(function(data){
	if (data.command == 'user_counter' && data.params[BX.message('SITE_ID')] && data.params[BX.message('SITE_ID')]['__НАЗВАНИЕ_ВАШЕГО_СЧЕТЧИКА__'])
	{
		// вызвать код для обновления счетчика
		// в data.params[BX.message('SITE_ID')]['__НАЗВАНИЕ_ВАШЕГО_СЧЕТЧИКА__'] будет новое значение счетчика
	}
}, this));Копировать
```

**Работа с модулем Push and Pull**

Ловушка для страниц десктопной версии (все события кроме событий online):

```
BX.addCustomEvent("onPullEvent-moduleName", BX.delegate(function(command,params){
	console.log('Events of moduleName', command, params);
}, this));Копировать
```

Ловушка для страниц мобильной версии (все события кроме событий online):

```
BX.addCustomEvent("onPull-moduleName", BX.delegate(function(data){
	console.log('Events of moduleName', data.command, data.params);
}, this));Копировать
```

**Примечание**: не забывайте сменить в примере "moduleName" на имя вашего модуля.

Пример кода для работы с [PHP классами](/api_help/push_pull/classes/index.php) модуля (Pull, Pull Shared, Pull Watch):

```
BX.addCustomEvent("onPullEvent-main", function(module_id,command,params) {
	if (command == 'check')
	{
		console.log('Command from module MAIN - its work!');
	}
});Копировать
```

В примере иы подписываемся на событие получение команд (**onPullEvent-moduleName**), moduleName это название вашего модуля, например **main**, в функции получаем command, params которые мы указали при отправке команды из PHP, обрабатываем свои команды с учетом вашей логики.

Если ваша логика требует сбора всех событий, то формат немного отличается: (доступно на любой версии **pull**)

Ловушка для страниц десктопной версии (все события кроме событий online):

```
BX.addCustomEvent("onPullEvent", BX.delegate(function(module_id,command,params){
	console.log(module_id, command, params);
}, this));Копировать
```

Ловушка для страниц мобильной версии (все события кроме событий online):

```
BX.addCustomEvent("onPull", BX.delegate(function(data){
	console.log(data.module_id, data.command, data.params);
}, this));Копировать
```

Пример кода для работы с [PHP классами](/api_help/push_pull/classes/index.php) модуля (Pull, Pull Shared, Pull Watch):

```
BX.addCustomEvent("onPullEvent", function(module_id,command,params) {
	if (module_id == "test" && command == 'check')
	{
		console.log('Work!');
	}
});Копировать
```

В примере мы подписываемся на событие получение команд (**onPullEvent**), в функции получаем **module\_id**, **command**, **params** которые мы указали при отправке команды из PHP, обрабатываем свои команды с учетом вашей логики.

**Примечания**:

* Для получения данных об онлайне используйте событие [link=888232]onPullOnlineEvent[/link]
* Лучше использовать обработчики событий для конкретных модулей, вместо обработчика на все события. Такой формат будет более производителен.

Новинки документации в соцсетях: