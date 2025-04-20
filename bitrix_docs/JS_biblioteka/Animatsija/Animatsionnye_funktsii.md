[JS библиотека](/api_help/js_lib/index.php)

[Анимация](/api_help/js_lib/animation/index.php)

Анимационные функции

Анимационные функции
====================

#### EaseIn-функции

Стандартно **BX.easing** поддерживает 9 видов функций (линейная, квадратная, кубическая и др.), которые позволяют делать различного вида плавные анимации:

* BX.easing.transitions.linear
* BX.easing.transitions.quad
* BX.easing.transitions.cubic
* BX.easing.transitions.quart
* BX.easing.transitions.quint
* BX.easing.transitions.bounce
* BX.easing.transitions.elastic
* BX.easing.transitions.back
* BX.easing.transitions.circ

Наглядно посмотреть как работает анимация этих функций можно [здесь](http://easings.net/ru).

#### EaseOut и EaseInOut-фунции

Следующие два статических метода переобразуют easeIn-функцию в easeOut-функцию и easeInOut-функцию соответственно. Таким образом BX.easing стандартно поддерживает 27 видов анимаций.

```
BX.easing.makeEaseInOut(easingFunction)Копировать
```

```
BX.easing.makeEaseOut(easingFunction)Копировать
```

Можно определить и свою собственную функцию:

```
(new BX.easing({
	duration : 1200,
	start:{opacity: 0},
	finish:{opacity: 100},
	transition: function(progress) {
		return Math.abs(Math.sin(3 * Math.PI * progress / 2));
	},
	step : function(state){
		node.style.background = 'rgba(242,245,220,'+(state.opacity/100)+')'
	},
	complete: function()
	{
		node.style.background = '#f2f5dc';
	}
})).animate();Копировать
```

Здесь **progress** и возвращаемое значение функции - это состояние анимации от 0 до 1.

Новинки документации в соцсетях: