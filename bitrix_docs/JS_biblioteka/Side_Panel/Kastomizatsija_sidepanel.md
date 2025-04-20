[JS библиотека](/api_help/js_lib/index.php)

[Side Panel](/api_help/js_lib/sidepanel/index.php)

Кастомизация sidepanel

Кастомизация sidepanel
======================

Показ слайдера абстрагирован от шаблона сайта, на котором он показывается. Для конкретного шаблона сайта можно изменить параметры появления слайдера, а также настроить конфликтующие элементы дизайна. Для этого необходимо создать JavaScript-класс, наследующий [BX.SidePanel.Slider](/api_help/js_lib/sidepanel/sidepanel_slider.php) и переопределить соответствующие методы.

```
(function() {
"use strict";
BX.namespace("BX.MyModule.Slider");
BX.MyModule.Slider = function(url, options)
{
	BX.SidePanel.Slider.apply(this, arguments);
};
BX.MyModule.Slider.prototype =
{
	__proto__: BX.SidePanel.Slider.prototype,
	constructor: BX.MyModule.Slider,
	/**
	* @public
	* @returns {void}
	*/
	applyHacks: function()
	{
		//Код, настраивающий конфликтующие элементы дизайна 
		//Метод вызывается до отключения скроллинга страницы
	},
	/**
	* @public
	* @returns {void}
	*/
	applyPostHacks: function()
	{
		//Код, настраивающий конфликтующие элементы дизайна
		//Метод вызывается после отключения скроллинга страницы
	},
	/**
	* @public
	* @returns {void}
	*/
	resetHacks: function()
	{
		//Метод для сброса настроек, которые были сделаны в applyHacks
	},
	/**
	* @public
	* @returns {void}
	*/
	resetPostHacks: function()
	{
		//Метод для сброса настроек, которые были сделаны в applyPostHacks
	},
	/**
	* @public
	* @returns {number}
	*/
	getTopBoundary: function()
	{
		//Определяет верхнюю границу (координату) слайдера
		return 0;
	},
	/**
	* @public
	* @returns {number}
	*/
	getLeftBoundary: function()
	{
		//Определяет левую границу (координату) слайдера
		return 200;
	},
	/**
	* @public
	* @returns {number}
	*/
	getRightBoundary: function()
	{
		//Определяет правую границу (координату) слайдера
	return 0;
	}
};
})();Копировать
```

Далее необходимо зарегистрировать созданный класс.

```
BX.SidePanel.Manager.registerSliderClass("BX.MyModule.Slider");Копировать
```

Новинки документации в соцсетях: