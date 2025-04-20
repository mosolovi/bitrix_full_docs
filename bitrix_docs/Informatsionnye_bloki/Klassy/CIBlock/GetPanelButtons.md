[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlock](/api_help/iblock/classes/ciblock/index.php)

GetPanelButtons (доступен с 8.5.1)

GetPanelButtons
===============

Включить вкладки

Описание и параметры

Смотрите также

### Описание и параметры

```
array
CIBlock::GetPanelButtons(
	int IBLOCK_ID=0,
	int ELEMENT_ID=0,
	int SECTION_ID=0,
	array arOptions=array()
);Копировать
```

Метод возвращает массив, описывающий набор кнопок для управления элементами инфоблока. Метод статический.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| IBLOCK\_ID | Идентификатор инфоблока, которому принадлежит элемент. |
| ELEMENT\_ID | Идентификатор текущего элемента информационного блока. |
| SECTION\_ID | Идентификатор раздела инфоблока (при наличии). |
| arOptions | Массив, содержащий локализацию названий и [всплывающих подсказок к ним](/api_help/iblock/fields.php#fiblocklang). Должен содержать секцию *LABELS*, в которой ключами будут названия действий с элементами и разделами информационных блоков с префиксами *TEXT* и *TITLE* (*ELEMENT\_ADD\_TEXT* и *ELEMENT\_ADD\_TITLE*).    Если массив отсутствует, то настройки локализации берутся из настроек информационных блоков, которые возвращаются методом [CIBlock::GetArrayByID](/api_help/iblock/classes/ciblock/GetArrayByID.php). |

#### Возвращаемое значение

Массив, описывающий набор кнопок (добавление, редактирование, настройка и пр.) с учётом уровней права доступа к информационным блокам.

### Смотрите также

* [Дополнительные параметры информационных блоков](/api_help/iblock/fields.php#fiblocklang)
* [CIBlock::GetArrayByID](/api_help/iblock/classes/ciblock/GetArrayByID.php)

Новинки документации в соцсетях: