[JS библиотека](/api_help/js_lib/index.php)

[Side Panel](/api_help/js_lib/sidepanel/index.php)

[События](/api_help/js_lib/sidepanel/events/index.php)

Список событий

Список событий
==============

| Событие | Описание | С версии |
| --- | --- | --- |
| SidePanel.Slider:onOpen | Вызывается перед началом открытия слайдера. Есть возможность отменить открытие. |  |
| SidePanel.Slider:onOpenComplete | Вызывается, когда слайдер полностью "выехал" на странице. Контент слайдера может быть еще не загружен к этому моменту. |  |
| SidePanel.Slider:onLoad | Вызывается, когда контент слайдера загружен. |  |
| SidePanel.Slider:onClose | Вызывается перед закрытием слайдера. Есть возможность отменить закрытие. Пример отмены закрытия^  ``` BX.addCustomEvent("SidePanel.Slider:onClose", function(event) { 	if (event.getSlider().getUrl() === "calendar:settings") //для глобальных обработчиков проверяем свой слайдер 	{ 		event.denyAction(); 	} });Копировать ``` |  |
| SidePanel.Slider:onCloseComplete | Вызывается, когда слайдер полностью закрылся. |  |
| SidePanel.Slider:onCloseByEsc | Вызывается перед закрытием слайдера по клавише Escape. Есть возможность отменить закрытие. Событие происходит до onClose. |  |
| SidePanel.Slider:onDestroy | Вызывается перед уничтожением слайдера. |  |
| SidePanel.Slider:onFrameFocus | Вызывается при любом фокусе на iframe-странице. |  |

Новинки документации в соцсетях: