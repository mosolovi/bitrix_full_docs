[JS библиотека](/api_help/js_lib/index.php)

[Ядро библиотеки](/api_help/js_lib/kernel/index.php)

Кастомные события

Кастомные события
=================

Включить вкладки

Описание и методы

Примеры

### Описание и методы

Библиотека позволяет генерировать свои собственные события и отслеживать их возникновение при помощи обработчиков. Для этого применяются следующие методы.

| Метод | Описание | С версии |
| --- | --- | --- |
| [BX.addCustomEvent](/api_help/js_lib/kernel/castom_events/bx_addcustomevent.php) | Назначает обработчик кастомному событию. |  |
| [BX.removeCustomEvent](/api_help/js_lib/kernel/castom_events/bx_removecustomevent.php) | Удаляет обработчик кастомного события. |  |
| [BX.onCustomEvent](/api_help/js_lib/kernel/castom_events/bx_oncustomevent.php) | Вызывает все обработчики события для объекта. |  |
| [BX.PULL.extendWatch](/api_help/push_pull/classes/bx_pull_extendwatch/index.php) | Продление подписки на тег. (Работает в модуле [Push and Pull](/api_help/push_pull/index.php)) | 14.0 |

### Примеры

```
function Animal(name, diet)
{
	this.name = name;
	this.diet = diet == 'carnivore' ? 'carnivore' : 'herbivore';
}
Animal.prototype.Hungry = function()
{
	if(this.diet == 'carnivore')
		this.Hunt();
	else
		this.Pasture();
}
Animal.prototype.Hunt = function()
{
	BX.addCustomEvent('onAnimalPasture', BX.proxy(function(prey){
		console.log(this.name + ' catches ' + prey.name);
		this.Eat(prey.name);
	}, this));
}
Animal.prototype.Pasture = function()
{
	this.Eat('grass');
	BX.onCustomEvent(this, 'onAnimalPasture', [this]);
}
Animal.prototype.Eat = function(food)
{
	console.log(this.name + ' eats ' + food);
}
var wolf = new Animal('wolf', 'carnivore'),
	deer = new Animal('deer', 'herbivore');
wolf.Hungry();
deer.Hungry();Копировать
```

Новинки документации в соцсетях: