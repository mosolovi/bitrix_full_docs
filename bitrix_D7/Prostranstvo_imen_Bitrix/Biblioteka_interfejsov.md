[Пространство имён Bitrix](/api_d7/bitrix/index.php)

[Библиотека интерфейсов](/api_d7/bitrix/ui/index.php)

UI-библиотека

UI-библиотека
=============

Включить вкладки

Расширения

Компоненты

Примеры

UI-библиотека (user interface) — это библиотека пользовательских интерфейсов. Основная задача модуля — стандартизировать и централизовать управление стилями и поведением типовых элементов, таких как: кнопки, формы, иконки, табы и так далее.
  
  
Модуль несет системный характер. Его нельзя ни отключить, ни удалить. Он подключается автоматически при его использовании. Остальное время модуль неактивен.

### Расширения

| Название | Описание |
| --- | --- |
| [color\_picker](/api_d7/bitrix/ui/color_picker/introduction.php) | Диалог выбора цвета |
| [spotlight](/api_d7/bitrix/ui/spotlight/introduction.php) | Элемент интерфейса в виде пульсирующего круга |
| [ui.advice](/api_d7/bitrix/ui/ui_advice.php) | Блок с советом |
| [ui.alerts](/api_d7/bitrix/ui/messages/alerts.php) | Сообщения |
| [ui.banner-dispatcher](/api_d7/bitrix/ui/ui_banner_dispatcher.php) | Диспетчер баннеров |
| [ui.buttons](/api_d7/bitrix/ui/buttons/button.php) | Кнопки |
| [ui.confetti](/api_d7/bitrix/ui/confetti/index.php) | Конфетти |
| [ui.countdown](/api_d7/bitrix/ui/ui_countdown.php) | Таймер обратного отсчета |
| [ui.counter](/api_d7/bitrix/ui/counter/index.php) | Счетчики |
| [ui.dialogs.checkbox-list](/api_d7/bitrix/ui/ui_dialogs_checkbox_list.php) | Попап с чекбоксами для настройки вывода вашего контента |
| [ui.dialogs.messagebox](/api_d7/bitrix/ui/dialogs/index.php) | Создание стандартных диалогов типа alert и confirm |
| [ui.ears](/api_d7/bitrix/ui/ears/index.php) | Кнопки прокрутки «уши» |
| [ui.entity-catalog](/api_d7/bitrix/ui/entity_catalog/intro.php) | Каталог элементов |
| [ui.entity-selector](/api_d7/bitrix/ui/entity_selector/index.php) | Диалог выбора сущностей |
| [ui.feedback.form](/api_d7/bitrix/ui/feedback_form/index.php) | Формы обратной связи |
| [ui.forms](/api_d7/bitrix/ui/forms/common.php) | Формы |
| [ui.hint](/api_d7/bitrix/ui/hint/index.php) | Подсказки |
| [ui.icons](/api_d7/bitrix/ui/icons/common.php) | Иконки |
| [ui.icon-set](/api_d7/bitrix/ui/icon_set/index.php) | Сет иконок из библиотеки |
| [ui.inputmask](/api_d7/bitrix/ui/ui_inputmask.php) | Маска ввода |
| [ui.label](/api_d7/bitrix/ui/labels/index.php) | Метки |
| [ui.layout-form](/api_d7/bitrix/ui/layout_form/index.php) | Формы с сеткой |
| [ui.menu-configurable](/api_d7/bitrix/ui/menu_configurable/index.php) | Настраиваемое меню |
| [ui.notification](/api_d7/bitrix/ui/notification/start.php) | Нотификации |
| [ui.progressbar](/api_d7/bitrix/ui/progressbar/common.php) | ПрогрессБар |
| [ui.progressround](/api_d7/bitrix/ui/progressbar/api_progressround.php) | Круглый ПрогрессБар |
| [ui.reactions-select](/api_d7/bitrix/ui/reactions_select/index.php) | Компонент для выбора реакции |
| [ui.select](/api_d7/bitrix/ui/select/index.php) | Компонент для выбора элемента из списка |
| [ui.sidepanel-content](/api_d7/bitrix/ui/sidepanel_content/index.php) | Типовое использование контентного слайдера |
| [ui.sidepanel.layout](/api_d7/bitrix/ui/sidepanel_layout/index.php) | Верстка контентного слайдера |
| [ui.stageflow](/api_d7/bitrix/ui/stageflow/stageflow.php) | Отрисовка последовательности стадий в верхней карточке элемента |
| [ui.stepbystep](/api_d7/bitrix/ui/stepbystep/index.php) | Компонент-обёртка для пошаговых блоков |
| [ui.stepprocessing](/api_d7/bitrix/ui/stepprocessing/basics.php) | Диалог для пошагового процесса |
| [ui.textanimate](/api_d7/bitrix/ui/textanimate/index.php) | Анимация смены текста |
| [ui.textcrop](/api_d7/bitrix/ui/textcrop/index.php) | Сокращение текста по высоте |
| [ui.timeline](/api_d7/bitrix/ui/timeline/timelineitem.php) | Таймлайн |
| [ui.toolbar](/api_d7/bitrix/ui/toolbar/get_started.php) | Тулбар |
| [ui.tooltip](/api_d7/bitrix/ui/tooltip/index.php) | Тултип с карточкой пользователя |
| [ui.tour](/api_d7/bitrix/ui/tour/index.php) | Тур |
| [ui.video-player](/api_d7/bitrix/ui/uivideoplayer/index.php) | Видеоплеер |
| [ui.viewer](/api_d7/bitrix/ui/viewer/index.php) | Просмотрщик |
| [ui.userfield](/api_d7/bitrix/ui/userfield/userfield.php) | Модель настроек пользовательского поля |
| [ui.userfieldfactory](/api_d7/bitrix/ui/userfield/userfieldfactory.php) | Фабрика настроек пользовательских полей |

### Компоненты

| Название | Описание |
| --- | --- |
| [bitrix:spotlight](/api_d7/bitrix/ui/spotlight/bitrix_spotlight.php) | Выводит подсказку на странице около указанного DOM-элемента |
| [bitrix:ui.sidepanel.wrapper](/api_d7/bitrix/ui/sidepanel_wrapper/start.php) | Является оберткой для вывода целевого компонента в слайдере |
| [bitrix:ui.button.panel](/api_d7/bitrix/ui/button_panel/start.php) | Выводит панель с кнопками отправки формы |
| [bitrix:ui.toolbar](/api_d7/bitrix/ui/toolbar/get_started.php) | Выводит тулбар с кнопками и фильтром |
| [bitrix:ui.tour](/api_d7/bitrix/ui/tour/component.php) | Выводит подсказку на странице около указанного DOM-элемента |

### Примеры

Универсальный пример получения доступа к API поля. С помощью этого API устанавливаются значения, удаляются значения и так далее.

```
// Получаем ссылку на DOM-элемент поля
var element = document.querySelector("[data-name=\"sEmployeeGroup\"]");
// Получаем запись из BX.Main.ui.Factory
var field = BX.Main.ui.Factory.get(element);
if (field)
{
	// Получаем ссылку на экземпляр класса поля
	var fieldInstance = field.instance;
    
	// Далее можно использовать API:
	// Установка значения для поля типа main-ui-select
	fieldInstance.updateValue(fieldInstance.getItems()[0]);
	fieldInstance.updateDataValue(fieldInstance.getItems()[0]);
	// Установка значения для поля типа main-ui-multi-select
	fieldInstance.selectItem(fieldInstance.getItems()[0]);
	// Удаление значения для поля типа main-ui-multi-select
	fieldInstance.unselectItem(fieldInstance.getItems()[0]);
}Копировать
```

Как через js библиотеку BX поменять настройки фильтра на странице.

```
var filter = BX.Main.filterManager.getById('my_filter_id');
if (filter) {
	var filterApi = filter.getApi();
	filterApi.setFields({'NAME': 'main 17.0.7'});
	filterApi.apply();
}Копировать
```

  

#### Смотрите также:

* [Стандартные диалоги Alert и Confirm](https://dev.1c-bitrix.ru/api_help/js_lib/dialogs/index.php)
* [SidePanel - Слайдер](https://dev.1c-bitrix.ru/api_help/js_lib/sidepanel/index.php)

Новинки документации в соцсетях: