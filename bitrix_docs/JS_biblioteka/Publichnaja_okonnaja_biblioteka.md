[JS библиотека](/api_help/js_lib/index.php)

Публичная оконная библиотека

Публичная оконная библиотека
============================

Используется расширение **popup** (**core\_popup.js**). Данный вид окон используется для работы публичный интерфейсов. Для административных интерфейсов (в т.ч. и для административных интерфейсов в публичной части) следует использовать расширение [window](/api_help/js_lib/window/index.php).

#### Пример

```
<?
require($_SERVER["DOCUMENT_ROOT"]."/bitrix/header.php");
$APPLICATION->SetTitle("PopUp");
	CJSCore::Init(array("popup"));
?>
<div id="hideBlock" style="display:none;">
	<h1>Hello</h1>
	<p>text</p>
</div>
<script>
	window.BXDEBUG = true;
BX.ready(function(){
	var oPopup = new BX.PopupWindow('call_feedback', window.body, {
		autoHide : true,
		offsetTop : 1,
		offsetLeft : 0,
		lightShadow : true,
		closeIcon : true,
		closeByEsc : true,
		overlay: {
			backgroundColor: 'red', opacity: '80'
		}
	});
	oPopup.setContent(BX('hideBlock'));
	BX.bindDelegate(
		document.body, 'click', {className: 'css_popup' },
			BX.proxy(function(e){
				if(!e)
					e = window.event;
				oPopup.show();
				return BX.PreventDefault(e);
		}, oPopup)
	);
   
   
});
</script>
<div class="css_popup">click Me</div>
<?require($_SERVER["DOCUMENT_ROOT"]."/bitrix/footer.php");?>Копировать
```

Новинки документации в соцсетях: