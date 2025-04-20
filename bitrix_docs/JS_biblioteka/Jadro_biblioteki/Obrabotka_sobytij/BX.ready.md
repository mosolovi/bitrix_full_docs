[JS библиотека](/api_help/js_lib/index.php)

[Ядро библиотеки](/api_help/js_lib/kernel/index.php)

[Обработка событий](/api_help/js_lib/kernel/events/index.php)

BX.ready

BX.ready
========

```
void 
BX.ready(
	Function handler
);Копировать
```

Функция добавляет обработчик события **DOM-структура доступна для записи**. Более короткий вариант – `BX(Function handler)`.

#### Пример

```
<?
require($_SERVER["DOCUMENT_ROOT"]."/bitrix/header.php");
$APPLICATION->SetTitle("События");
	CJSCore::Init();
?>
<a href="http://1c-bitrix.ru" class="css_bind" data-param="HELLO" >click Me</a>
<div class="css_bind" data-param="HELLO2">click Me2</div>
<script>
BX.ready(function(){
	var param1 = ' global Hello';
	BX.bindDelegate(
		document.body, 'click', {className: 'css_bind' },
		function(e){
			if(!e)
				e = window.event;
         
			alert(this.getAttribute('data-param')+param1);
			return BX.PreventDefault(e);
		}
	);
});
</script>
<?require($_SERVER["DOCUMENT_ROOT"]."/bitrix/footer.php");?>Копировать
```

Новинки документации в соцсетях: