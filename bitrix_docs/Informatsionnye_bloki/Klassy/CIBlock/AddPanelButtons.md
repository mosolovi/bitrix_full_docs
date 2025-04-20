[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlock](/api_help/iblock/classes/ciblock/index.php)

AddPanelButtons (доступен с 8.5.1)

AddPanelButtons
===============

```
CIBlock::AddPanelButtons(
	string mode,
	string componentName,
	array arButtons
);Копировать
```

Метод добавляет в панель управления кнопки, отвечающие за управление элементами инфоблока (в методе производится вызов [CMain::AddPanelButton](/api_help/main/reference/cmain/addpanelbutton.php)). Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| mode | Режим отображения административной панели. Возвращается методом [CMain::GetPublicShowMode](/api_help/main/reference/cmain/GetPublicShowMode.php). |
| componentName | Название компонента, который регистрирует кнопки. Возвращается методом [CBitrixComponent::GetName](/api_help/main/reference/cbitrixcomponent/getname.php). |
| arButtons | Массив кнопок, которые можно зарегистрировать с учётом текущих прав пользователя. Формируется методом [CIBlock::GetPanelButtons](/api_help/iblock/classes/ciblock/getpanelbuttons.php). |

#### Смотрите также

* [CMain::AddPanelButton](/api_help/main/reference/cmain/addpanelbutton.php)
* [CMain::GetPublicShowMode](/api_help/main/reference/cmain/GetPublicShowMode.php)
* [CBitrixComponent::GetName](/api_help/main/reference/cbitrixcomponent/getname.php)
* [CIBlock::GetPanelButtons](/api_help/iblock/classes/ciblock/getpanelbuttons.php)

Новинки документации в соцсетях: