Push and Pull

Push and Pull
=============

Включить вкладки

Описание

Примеры

### Описание

Модуль позволяет организовать транспорт для отправки мгновенных команд. Реализация данного функционала в виде отдельного модуля позволяет любому модулю (в том числе и модулям сторонних разработчиков) используя API отправлять мгновенные нотификации и сообщения клиентам.

Подключение модуля:

```
if (!CModule::IncludeModule('pull'))
	return false;Копировать
```

Так же необходимо зарегистрировать зависимость на модуль **Push and Pull**. Регистрация обработчика зависимости:

```
RegisterModuleDependences("pull", "OnGetDependentModule", "your_module", "CYourModulePullSchema", "OnGetDependentModule" );Копировать
```

События и push-уведомления они отправляются на серверы рассылки в эпилоге страницы. Если вы отправляете события в ajax-обработчиках, вам необходимо использовать *CMain::FinalActions()* в финале обработчика.

### Примеры

**Пример кода класса**

```
class CYourModulePullSchema
{
	public static function OnGetDependentModule()
	{
		return Array(
			'MODULE_ID' => "your_module",
			'USE' => Array("PUBLIC_SECTION")
		);
	}
}Копировать
```

Для работы с командами, отправленными из PHP необходимо в вёрстке использовать следующие JS код:

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