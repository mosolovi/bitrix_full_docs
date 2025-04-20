[JS библиотека](/api_help/js_lib/index.php)

[Публичная оконная библиотека](/api_help/js_lib/popup/index.php)

BX.PopupWindowManager

BX.PopupWindowManager
=====================

**BX.PopupWindowManager** - обертка над BX.PopupWindow. Имеет две особенности в использовании:

* Повторный вызов метода **create** - вернет уже существующий объект.
* Открытие диалога, автоматически закрывает другой открытый диалог, созданный через BX.PopupWindowManager.

| Метод | Описание | С версии |
| --- | --- | --- |
| create(uniquePopupId, bindElement, params) | Создает диалог. Точно также как и BX.PopupMenu. |  |
| isPopupExists(uniquePopupId) | Проверяет существование диалога. |  |
| getCurrentPopup() | Получает текущий диалог. |  |

#### Пример

```
var popup = BX.PopupWindowManager.create("popup-message", null, {
	content: "Hello World!",
	darkMode: true,
	autoHide: true
});
popup.show();Копировать
```

Новинки документации в соцсетях: