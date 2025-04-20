[JS библиотека](/api_help/js_lib/index.php)

[Анимация](/api_help/js_lib/animation/index.php)

BX.easing.prototype.animateProgress

BX.easing.prototype.animateProgress
===================================

Редко используемый метод. Также как и метод **animate** запускает анимацию, но на каждой итерации вместо функции-обработчика **step**, вызывается функция-обработчик **progress**. Не использует наборы значений start и finish. Обработчику progress на каждой итерации передается значение, которое меняется от 0 в начале анимации до 1 в конце.

```
var button = BX("my-button");
var leftMax = 100;
var opacityMin = 0;
var easing = new BX.easing({
{
	duration : 4000,
	transition : BX.easing.makeEaseOut(BX.easing.transitions.quart),
	progress : function(progress)
	{
		button.style.left =  Math.round(leftMax * progress) + "px";
		button.style.opacity =  (100 + Math.round((opacityMin - 100) * progress)) / 100;
	},
	complete : function()
	{
		button.style.background = "green";
	}
});
easing.animateProgress();Копировать
```

Новинки документации в соцсетях: