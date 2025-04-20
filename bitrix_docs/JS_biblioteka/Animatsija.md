[JS библиотека](/api_help/js_lib/index.php)

Анимация

Анимация
========

Включить вкладки

Описание и методы

Пример использования

### Описание и методы

Класс **BX.easing** позволяет создавать анимацию на странице. Анимация в контексте веб-страницы - это изменение стиля DOM-элемента.

Перед использованием методов класса BX.easing необходимо подключить расширение **core\_fx.js**.

```
CJSCore::Init(array("fx"));Копировать
```

| Метод | Описание | С версии |
| --- | --- | --- |
| [BX.easing](/api_help/js_lib/animation/easing.php) | Конструктор. | 12.5 |
| BX.easing.prototype.animate | Запускает анимацию. | 12.5 |
| [BX.easing.prototype.animateProgress](/api_help/js_lib/animation/easing_prototype_animateprogress.php) | Редко используемый метод. Запускает анимацию, но на каждой итерации вместо функции-обработчика **step**, вызывается функция-обработчик **progress**. | 12.5 |
| BX.easing.prototype.stop(completed) | Останавливает анимацию на текущем шаге. Если completed=true, то дополнительно выполнится функция-обработчик окончания анимации. | 12.5 |
| [Анимационные функции](/api_help/js_lib/animation/animation.php) | Функции, которые позволяют делать различного вида плавные анимации. | 12.5 |

### Пример использования

```
var banner = BX("my-banner");
var easing = new BX.easing({
	duration : 500,
	start : { height : 0, opacity : 0 },
	finish : { height : 100, opacity: 100 },
	transition : BX.easing.transitions.quart,
	step : function(state){
		banner.style.height = state.height + "px";
		banner.style.opacity = state.opacity/100;
	},
	complete : function() {
		banner.style.display = "none";
	}
});
easing.animate();Копировать
```

Новинки документации в соцсетях: