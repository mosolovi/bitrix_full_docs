[Поиск](/api_help/search/index.php)

[Классы](/api_help/search/classes/index.php)

[CSearchCustomRank](/api_help/search/classes/csearchcustomrank/index.php)

Поля объекта CSearchCustomRank

Поля объекта CSearchCustomRank
==============================

Класс CSearchCustomRank использует следующие поля при работе с объектом "Правило сортировки".

| Название поля | Описание | Тип | Обяз. |
| --- | --- | --- | --- |
| ID | Идентификатор правила. | int | Да. |
| SITE\_ID | Сайт для элементов которого данное правило будет применяться. | char(2) | Да. |
| MODULE\_ID | Идентификатор модуля для элементов которого данное правило будет применяться. | string(200) | Да. |
| PARAM1 | Первый параметр элемента. | text |  |
| PARAM2 | Второй параметр элемента. | text |  |
| ITEM\_ID | Идентификатор элемента поискового индекса. | string(255) |  |
| RANK | Вес. | int | Да. |
| APPLIED | Признак применения правила. | char(1) | Да. |

Новинки документации в соцсетях: