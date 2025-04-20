[JS библиотека](/api_help/js_lib/index.php)

[Side Panel](/api_help/js_lib/sidepanel/index.php)

BX.SidePanel.Instance

BX.SidePanel.Instance
=====================

Включить вкладки

Метод BX.SidePanel.Instance.open

Метод BX.SidePanel.Instance.bindAnchors(anchors)

Класс - основной программный интерфейс для работы со слайдером. Является объектом-синглтоном.

### Метод BX.SidePanel.Instance.open

```
BX.SidePanel.Instance.open(
	url[,
	options]
)Копировать
```

Метод открывает в слайдере страницу с указанным адресом в параметре url. Возвращает *true*, если слайдер успешно открылся, иначе *false*.

#### Параметры

| Параметр | Описание | Тип |
| --- | --- | --- |
| url | Адрес страницы, которая будет открыта в iframe'е слайдера. Для слайдеров со своим контентом (указана опция contentCallback) в этом параметре указывается уникальный идентификатор. | string |
| options | Коллекция опций слайдера. Все настройки являются необязательными.  * **contentCallback {function(BX.SidePanel.Slider)}** - Функция-callback, загружающая в слайдер произвольное содержимое. В первом аргументе принимает объект слайдера (экземпляр класса [BX.SidePanel.Slider](/api_help/js_lib/sidepanel/sidepanel_slider.php)). Callback должен внутри себя:   + Создать и вернуть промис (`new Promise(function(resolve, reject) {})`).   + Разрешить его (`resolve(content)`) с содержимым слайдера с содержимым слайдера (строка или DOM-элемент).   + В случае ошибки сообщить об этом (`reject(error)`). * **width {number}** - Максимальная ширина слайдера. * **cacheable {boolean}** - Кешировать слайдер после закрытия. Если указано *false*, при закрытии слайдер будет автоматически уничтожен. По умолчанию *true*. * **autoFocus {boolean}** - При открытии слайдера происходит автоматическая фокусировка на iframe'е. Это поведение можно отменить, если указать *false*. * **allowChangeHistory {boolean}** - Менять адрес страницы на адрес открытого слайдера. По умолчанию *true*. * **allowChangeTitle {true|false|null}** - Менять заголовок страницы на заголовок открытого слайдера. По умолчанию *null*. При не установленном значении (*null*), название страницы будет меняться, если у слайдера явно задан заголовок (опция *title*) или разрешена смена адреса страницы (**allowChangeHistory**). * **allowCrossOrigin {true|false|null}** - Открывать сторонние сайты в слайдере.   + Для открытия внешнего сайта передать *true*.     `BX.SidePanel.Instance.open('http://testfiles.a-team.bx/demo/sidepanel.php?forceLoad=y', {cacheable: false, allowCrossOrigin: true})`   + Для того, чтобы закрыть слайдер изнутри, то есть инициировать во внешнем сайте, нужно выполнить такой код:      ```     if (window.parent)     {         parent.postMessage('BX:SidePanel:close', document.referrer);     }     Копировать     ```   + Чтобы просигнализировать слайдеру, что не нужно показывать лоадер до загрузки всех ресурсов, а показать по мере готовности:      ```     if (window.parent)     {         parent.postMessage('BX:SidePanel:load:force', document.referrer);     }Копировать     ```   + Если нужно из стороннего сайта отправить данные на портал:      ```     if (window.parent)     {         parent.postMessage({type: 'BX:SidePanel:data:send', data: {key1: 'data 1', key2: 'data 2'}}, document.referrer);     }Копировать     ```   + Чтобы портал мог получить эти данные, нужно добавить обработчик события `onXDomainMessage` при вызове слайдера      ```     BX.SidePanel.Instance.open(         'https://cross-domain',         {             cacheable: false,             allowCrossOrigin: true,             events: {                 onXDomainMessage: (event: BX.SidePanel.MessageEvent) => {                     const { command } = event.getData();                     if (command === 'showHelper')                     {                         BX.Helper.show();                     }                 }             }         }     )Копировать     ```   + **Title {string}** - Заголовок страницы. Если не указан, значение берется из **document.title**.   + **requestMethod {string}** - Если параметр равен *post*, то в iframe'е слайдера страница загрузится HTTP-методом POST. Это может понадобится для передачи большого объема данных, так как HTTP-метод GET может привести к ошибке `414 Request-URI Too Large`.   + **requestParams {object}** - POST-параметры передаваемые в запросе. Имеет смысл только при `requestMethod="post"`.   + **loader {string}** - Идентификатор лоадера вида **moduleId:loaderId** или путь к svg-файлу.   + **data {object}** - Произвольный набор своих данных для слайдера, с которыми можно работать (чтение/запись/удаление) на всем жизненном цикле.   + **label {object}** - Опция задает настройки для внешнего вида лейбла ("этикетки") слайдера. Объект вида:       ```     label: {     	text: "Моя этикетка",     	color: "#FFFFFF", //цвет текста     	bgColor: "#2FC6F6", //цвет фона     	opacity: 80 //прозрачность фона     }Копировать     ```   + **animationDuration {number}** - Время анимации открытия/закрытия слайдера в миллисекундах.   + **events {object.}** - Коллекция обработчиков событий. | Object |

#### Примеры использования

Пример слайдера со своим содержимым и данными.

```
BX.SidePanel.Instance.open("crm:activity-view", {
	//Пробрасываем свои данные в слайдер
	data: {
		minRepeats: 30,
		maxRepeats: 100,
		repeatString: "=========="
	},
	contentCallback: function(slider) {
		var promise = new BX.Promise();
		//Эмуляция асинхронной операции (как правило, это ajax)
		setTimeout(function() {
			//Читаем свои данные
			var minRepeats = slider.getData().get("minRepeats");
			var maxRepeats = slider.getData().get("maxRepeats");
			var repeatString = slider.getData().get("repeatString");
			var repeats = Math.floor(Math.random() * (maxRepeats - minRepeats) + minRepeats);
			slider.getData().set("repeats", repeats); //Записываем новые данные
			var result =
				"minRepeats: " + minRepeats + "<br>" +
				"maxRepeats: " + maxRepeats + "<br>" +
				"repeats: " + repeats + "<br><br>" +
				(repeatString + "<br>").repeat(repeats)
			;
			promise.fulfill(result);
		}, 1000);
		return promise;
	},
	animationDuration: 100,
	width: 600,
	events: {
		onLoad: function(event) {
			var slider = event.getSlider();
			console.log(slider.getData().get("repeats")); //Читаем записанные данные
		}
	}
});Копировать
```

Открытие слайдера HTTP-методом POST.

```
BX.SidePanel.Instance.open("/mypage.php", {
	requestMethod: "post",
	requestParams: { // post-параметры
		action: "load",
		ids: [1, 2, 3],
		dictionary: {
			one: 1,
			two: 2
		}
	}
});Копировать
```

### Метод BX.SidePanel.Instance.bindAnchors(anchors)

```
BX.SidePanel.Instance.bindAnchors(
	anchors
)Копировать
```

Метод регистрирует правила обработки нажатия ссылок на странице.

#### Параметры

| Метод | Описание | Тип |
| --- | --- | --- |
| anchors | Настройки механизма обработки нажатия ссылок.  * **rules {Array}**  - Массив правил. Каждое правило - объект со следующими ключами:   + **condition {string[]|RegExp[]}** - Массив шаблонов (регулярных выражений) ссылок. Обязательный параметр.   + **options {Object}** - Коллекция опций, с которыми откроется слайдер. См. BX.SidePanel.Instance.open.   + **stopParameters {string[]}** - Массив запрещенных параметров. Если адрес содержит хотя бы один из этих параметров, ссылка обработана не будет. Необязательный параметр.   + **handler {function(event, link)}** - Функция-обработчик нажатия на ссылку. С помощью этого параметра можно переопределить поведение по умолчанию (открытие слайдера). Необязательный параметр.     - **event {MouseEvent}** - Объект события нажатия на ссылку     - **link** - Объект с данными ссылки:       * **href** - Адрес ссылки.       * **target**  - Значение атрибута target.       * **anchor**  - DOM-объект ссылки (тег <a>).       * **matches** - Массив с совпадениями групп регулярного выражения.   + **validate {function(link)}** - Функция проверки корректности ссылки. Если возвращает *false*, ссылка обработана не будет. Необязательный параметр.     - **link** - объект с данными ссылки.   + **allowCrossDomain {boolean}** Разрешить открывать ссылки с внешних сайтов. По умолчанию *false*.   + **mobileFriendly {boolean}** Обрабатывать ссылки в мобильных браузерах. По умолчанию *false*. | Object |

#### Другие методы класса

| Метод | Описание | С версии |
| --- | --- | --- |
| ``` BX.SidePanel.Instance.isOpen()Копировать ``` | Возвращает *true*, если слайдер отображается на экране. |  |
| ``` BX.SidePanel.Instance.close([immediately=false])Копировать ``` | Закрывает текущий слайдер на странице.  **immediately {boolean}**Закрыть слайдер мгновенно, без анимации. |  |
| ``` BX.SidePanel.Instance.closeAll([immediately=false])Копировать ``` | Закрывает все слайдеры на странице.  **immediately {boolean}** Закрыть слайдеры мгновенно, без анимации. |  |
| ``` BX.SidePanel.Instance.destroy(url)Копировать ``` | Уничтожает слайдер на странице.  **url {string}** Адрес страницы или идентификатор удаляемого слайдера. |  |
| ``` BX.SidePanel.Instance.reload()Копировать ``` | Перегружает текущий открытый слайдер. |  |
| ``` BX.SidePanel.Instance.getTopSlider()Копировать ``` | Возвращает текущий открытый слайдер (экземпляр класса [[BX.SidePanel.Slider](/api_help/js_lib/sidepanel/sidepanel_slider.php)). |  |
| ``` BX.SidePanel.Instance.getSlider(url)Копировать ``` | Возвращает слайдер (экземпляр класса [BX.SidePanel.Slider](/api_help/js_lib/sidepanel/sidepanel_slider.php)) по указанному адресу или идентификатору.  **url {string}** - Адрес страницы или идентификатор слайдера. |  |
| ``` BX.SidePanel.Instance.getSliderByWindow(window)Копировать ``` | Возвращает слайдер (экземпляр класса [BX.SidePanel.Slider](/api_help/js_lib/sidepanel/sidepanel_slider.php)) по окну iframe'а.  **window {Window}** - Объект окна iframe'а. |  |
| ``` BX.SidePanel.Instance.getOpenSliders()Копировать ``` | Возвращает список всех открытых слайдеров (массив экземпляров класса [BX.SidePanel.Slider](/api_help/js_lib/sidepanel/sidepanel_slider.php)). |  |
| ``` BX.SidePanel.Instance.getLastOpenSlider()Копировать ``` | Возвращает закрытый слайдер (экземпляр класса [BX.SidePanel.Slider](/api_help/js_lib/sidepanel/sidepanel_slider.php)). | Object |

Новинки документации в соцсетях: