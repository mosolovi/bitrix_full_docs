[Интернет-магазин](/api_help/sale/index.php)

[Классы](/api_help/sale/classes/index.php)

[CSaleUserAccount](/api_help/sale/classes/csaleuseraccount/index.php)

Add (доступен с 4.0.6)

Add
===

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
int
CSaleUserAccount::Add(
	array arFields
);Копировать
```

Метод добавляет новый счет пользователя в соответствии с параметрами из массива arFields. Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| arFields | Ассоциативный массив параметров нового счета. Может содержать следующие ключи:  * **USER\_ID** - код пользователя-владельца * **CURRENT\_BUDGET** - текущая сумма на счете * **CURRENCY** - валюта * **NOTES** - текстовое описание * **LOCKED** - флаг заблокированности счета * **DATE\_LOCKED** - дата блокировки счета |

#### Возвращаемые значения

Метод возвращает код добавленного счета или *false* в случае ошибки.

### Примеры использования

```
if($USER->IsAuthorized())
{
	$user_id = $USER->GetID();
	$arFields = Array("USER_ID" => $user_id, "CURRENCY" => "USD", "CURRENT_BUDGET" => 0);
	$accountID = CSaleUserAccount::Add($arFields);
}Копировать
```

Создание счета для текущего пользователя

```
if(!CSaleUserAccount::GetByUserID($USER->GetID(), "RUB")){
	$arFields = Array("USER_ID" => $USER->GetID(), "CURRENCY" => "RUB", "CURRENT_BUDGET" => 0);
	CSaleUserAccount::Add($arFields);  
}Копировать
```

Новинки документации в соцсетях: