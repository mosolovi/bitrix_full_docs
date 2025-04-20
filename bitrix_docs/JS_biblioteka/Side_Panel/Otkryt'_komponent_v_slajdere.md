[JS библиотека](/api_help/js_lib/index.php)

[Side Panel](/api_help/js_lib/sidepanel/index.php)

Открыть компонент в слайдере (с версии 20.5.462)

Открыть компонент в слайдере
============================

Когда необходимо открыть страницу внутри слайдера без iframe, то можно сделать так:

```
BX.SidePanel.Instance.open("widget:example-item", {
	contentCallback: function (slider) {
		return new Promise(function(resolve, reject) {
			BX.ajax.runAction('example.item.view', {
				data: {
					id: 2208
				}
			}).then(function(response) {
				resolve({ html: response.data.html });
			});
		});
	},
	animationDuration: 100,
	width: 370
});Копировать
```

Обратите внимание, что действие example.item.view, должно возвращать тип ответа [\Bitrix\Main\Engine\Response\Component](https://dev.1c-bitrix.ru/api_d7/bitrix/main/httpresponse/component.php).

Новинки документации в соцсетях: