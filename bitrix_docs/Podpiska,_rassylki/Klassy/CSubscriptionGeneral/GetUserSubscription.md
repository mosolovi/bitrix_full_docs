[Подписка, рассылки](/api_help/subscribe/index.php)

[Классы](/api_help/subscribe/classes/index.php)

[CSubscriptionGeneral](/api_help/subscribe/classes/csubscriptiongeneral/index.php)

GetUserSubscription (доступен с 3.0.5)

GetUserSubscription
===================

```
array
CSubscription::GetUserSubscription();Копировать
```

Метод возвращает массив полей подписки текущего пользователя.
Подписка определяется по Email, сохраненному в куках посетителя,
либо по Email авторизованного пользователя. Метод статический.

#### Параметры

Метод не имеет параметров.

#### Возвращаемые значения

Возвращается массив [полей объекта "Подписка"](/api_help/subscribe/classes/csubscriptiongeneral/csubscriptiongeneralfields.php).
Если подписка посетителя не найдена, то возвращается массив array("ID"=>0, "EMAIL"=>"").

#### Пример использования

```
//get current user subscription from cookies
$aSubscr = CSubscription::GetUserSubscription();
//get user's newsletter categories
$aSubscrRub = CSubscription::GetRubricArray(intval($aSubscr["ID"]));
//show subscription form
//.....
Копировать
```

Новинки документации в соцсетях: