[JS библиотека](/api_help/js_lib/index.php)

[Side Panel](/api_help/js_lib/sidepanel/index.php)

Sidepanel с произвольным содержимым

Sidepanel с произвольным содержимым
===================================

Кроме открытия страницы в iframe'е, слайдер может отобразить произвольный контент. Для этого в параметре **contentCallback** необходимо
указать функцию, которая с помощью промиса загрузит в слайдер содержимое.

```
BX.SidePanel.Instance.open("crm:activity-view", { 
	contentCallback: function(slider) {
	
		//Callback должен вернуть промис или HTML (строка или DOM-элемент)
		return new Promise(function(resolve, reject) {
	
			//Эмуляция асинхронной операции. Здесь может быть ajax-запрос
			setTimeout(function() {
	
				//Разрешаем промис передав ему содержимое слайдера (строка или DOM-элемент)
				resolve("content<br>".repeat(100));
	
			}, 1000);
		});
	}
});Копировать
```

Новинки документации в соцсетях: