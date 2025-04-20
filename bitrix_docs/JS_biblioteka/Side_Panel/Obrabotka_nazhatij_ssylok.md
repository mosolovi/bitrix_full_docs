[JS библиотека](/api_help/js_lib/index.php)

[Side Panel](/api_help/js_lib/sidepanel/index.php)

Обработка нажатий ссылок

Обработка нажатий ссылок
========================

Метод [BX.SidePanel.Instance.bindAnchors](/api_help/js_lib/sidepanel/sidepanel_instance.php#bindAnchors) задает правила обработки ссылок на странице. В момент нажатия на ссылку, слайдер сравнивает адрес в атрибуте href c зарегистрированными шаблонами. В случае совпадения, соответствующая страница открывается в iframe'е слайдера.

```
BX.SidePanel.Instance.bindAnchors({
	rules:
	[
		{
			condition: [
				"/company/personal/user/(\\d+)/tasks/task/view/(\\d+)/",
				"/workgroups/group/(\\d+)/tasks/task/view/(\\d+)/",
				"/extranet/contacts/personal/user/(\\d+)/tasks/task/view/(\\d+)/"
			],
			loader: "tasks:view-loader",
			//Игноривать ссылки, содержащие следующие параметры в Query String
			stopParameters: [
				"PAGEN_(\\d+)",
				"MID"
			]
		},
		{
			condition: [
				"/company/personal/user/(\\d+)/tasks/task/edit/0/",
				"/workgroups/group/(\\d+)/tasks/task/edit/0/",
				"/extranet/contacts/personal/user/(\\d+)/tasks/task/edit/0/"
			],
			loader: "tasks:new-loader"
		},
		{
			condition: [ 
				new RegExp("/crm/lead/details/[0-9]+/", "i") 
			],
        		loader: "crm:entity-details-loader"
		},
		{
			condition: [
				"/company/personal/user/(\\d+)/groups/create/"
			],
			loader: "intranet:group-create-loader",
			
			//Опции, с которыми откроется слайдер 
			options: {
				width: 1200
			}
		},
		{
			condition: [
				/\/online\/\?(IM_DIALOG|IM_HISTORY)=([a-zA-Z0-9_|]+)/i
			],
			//Собственный обработчик нажатия на ссылку.
			//Вместо слайдера откроется мессенджер
			handler: function(event, link)
			{
				if (!window.BXIM)
				{
					return;
				}
	
				var type = link.matches[1];
				var id = link.matches[2];
	
				if (type === "IM_HISTORY")
				{
					BXIM.openHistory(id);
				}
				else
				{
					BXIM.openMessenger(id);
				}
	
				event.preventDefault();
			}
		}
	]
});Копировать
```

BX.SidePanel.Instance.bindAnchors можно вызвать несколько раз. Новые правила будут добавлены к существующим.

Если требуется обрабатывать ссылки на всех страницах сайта, вызов BX.SidePanel.Instance.bindAnchors необходимо перенести в шаблон сайта.

Ссылки внутри iframe'а анализируются по тем же правилам, что и в родительской странице.

Ссылки с data-атрибутом **data-slider-ignore-autobinding** не обрабатываются.

По соображениям безопасности ссылки на другой домен не открываются в слайдере, однако, это поведение можно отменить опцией **allowCrossDomain=true**.

Обработка ссылок в мобильных браузерах не производится, отменить это можно опцией **mobileFriendly=true**.

В параметре **options** можно указать опции, с которыми откроется слайдер.

Слайдер открывается при совпадении шаблона ссылки и адреса в атрибуте href. Это поведение по умолчанию можно переопределить, указав в опции handler свою функцию-обработчик.

Новинки документации в соцсетях: