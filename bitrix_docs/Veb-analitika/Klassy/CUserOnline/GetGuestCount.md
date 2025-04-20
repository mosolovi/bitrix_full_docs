[Веб-аналитика](/api_help/statistic/index.php)

[Классы](/api_help/statistic/classes/index.php)

[CUserOnline](/api_help/statistic/classes/cuseronline/index.php)

GetGuestCount

GetGuestCount
=============

```
int
CUserOnline::GetGuestCount()Копировать
```

Возвращает количество [посетителей](/api_help/statistic/terms.php#guest), проявивших активность на сайте (совершивших [хит](/api_help/statistic/terms.php#hit)) за определённый интервал времени. Данный интервал времени задается в настройках модуля "Статистика" в параметре "Интервал посетителей в online (сек.)".

#### Параметры метода

Нет параметров.

#### Смотрите также

* [CTraffic::GetCommonValues](/api_help/statistic/classes/ctraffic/getcommonvalues.php)

#### Примеры использования

```
<?
echo "Сейчас на сайте посетителей: ".CUserOnline::GetGuestCount();
?>
Копировать
```

Новинки документации в соцсетях: