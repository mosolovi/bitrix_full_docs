...

[Side Panel](/api_help/js_lib/sidepanel/index.php)

[События](/api_help/js_lib/sidepanel/events/index.php)

Передача данных между слайдерами (с версии 17.5.2)

Передача данных между слайдерами
================================

Включить вкладки

Событие SidePanel.Slider:onMessage

Методы отправки данных

Параметры

Примеры

Класс

Между слайдерами можно передавать произвольные данные. Для отправки данных используются методы postMessage, postMessageAll и postMessageTop. Для приема сообщений - событие onMessage.

### Событие SidePanel.Slider:onMessage

Вызывается, когда в слайдер приходит сообщение из другого слайдера. В первый аргумент обработчика приходит объект события типа BX.SidePanel.MessageEvent

### Методы отправки данных

| Метод | Описание | С версии |
| --- | --- | --- |
| ``` BX.SidePanel.Instance.postMessage( 	source, 	eventId, 	data )Копировать ``` | Отсылает сообщение (данные) в предыдущий слайдер и родительскую страницу. |  |
| ``` BX.SidePanel.Instance.postMessageAll( 	source, 	eventId, 	data )Копировать ``` | Отсылает сообщение (данные) во все слайдеры и в родительскую страницу. |  |
| ``` BX.SidePanel.Instance.postMessageTop( 	source, 	eventId, 	data )Копировать ``` | Отсылает сообщение (данные) только в родительскую страницу. |  |

### Параметры

| Параметры | Описание | Тип |
| --- | --- | --- |
| source | Идентификатор слайдера-отправителя данных. Ссылка на слайдер (экземпляр класса BX.SidePanel.Slider) или идентификатор слайдера. В случае iframe'а может быть ссылка на окно (window). | string|window|BX.SidePanel.Slider |
| eventId | Идентификатор события. Используется для того, чтобы отличить события разных слайдеров в обработчике onMessage. | string |
| data | Данные для передачи в другой слайдер. | object |

### Примеры

Пример передачи данных из iframe'а в предыдущий слайдер.

```
BX.SidePanel.Instance.postMessage(window, "my-event-id", { title: "1234" });Копировать
```

Пример получения данных.

```
BX.SidePanel.Instance.open("/mypage.php", {
	events: {
		onMessage: function(event) {
			console.log(
				"onMessage",
				"sender", event.getSender().getUrl(),
				"slider", event.getSlider().getUrl(),
				"data", event.getData()
			);
		}
	}
});Копировать
```

### Класс

| Класс | Описание | С версии |
| --- | --- | --- |
| Класс [BX.SidePanel.MessageEvent](/api_help/js_lib/sidepanel/events/postmessage/sidehanel.messageevent.php) | Класс представляет сообщение, которое слайдеры посылают друг другу. |  |

Новинки документации в соцсетях: