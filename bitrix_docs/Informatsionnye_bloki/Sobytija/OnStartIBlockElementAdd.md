[Информационные блоки](/api_help/iblock/index.php)

[События](/api_help/iblock/events/index.php)

OnStartIBlockElementAdd (доступно с 7.1.8)

OnStartIBlockElementAdd
=======================

```
bool функция-обработчик(
	array &arParams 
);Копировать
```

Событие вызывается в методе [CIBlockElement::Add](/api_help/iblock/classes/ciblockelement/add.php) до добавления элемента инфоблока перед проверкой правильности заполнения полей.

#### Параметры

| Параметр | Описание |
| --- | --- |
| **arParams** | [Массив полей](/api_help/iblock/fields.php#felement) нового элемента информационного блока. |

**Обратите внимание, что** все параметры данного обработчика являются ссылками на исходные переменные. Поэтому если вы измените значение параметра внутри обработчика, это приведет к смене значения исходной переменной поступившей на вход функции-обработчика.

  

#### Смотрите также

* [CIBlockElement::Add](/api_help/iblock/classes/ciblockelement/add.php)
* [Обработка событий](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

Новинки документации в соцсетях: