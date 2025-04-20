[Реклама, баннеры](/api_help/advertising/index.php)

[Классы](/api_help/advertising/classes/index.php)

[CAdvContract](/api_help/advertising/classes/cadvcontract/index.php)

IsModuleAccess (3.3.4 Удален с версии 8.0.0)

IsModuleAccess
==============

```
boolean
CAdvContract::IsModuleAccess(
	char(1) permission
);Копировать
```

Метод возвращает true, если текущий пользователь имеет право, переданное в качестве параметра, иначе false.

#### Параметры метода

| Параметры | Описание |
| --- | --- |
| permission | Символ, отвечающий за то или иное право на модуль рекламы. Возможны следующие значения:  * D - доступ закрыт * K - работа с контрактами (рекламодатель) * R - просмотр всего без права изменения * T - управление баннерами * W - полный административный доступ |

Новинки документации в соцсетях: