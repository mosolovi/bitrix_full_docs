[Интернет-магазин](/api_help/sale/index.php)

[Классы](/api_help/sale/classes/index.php)

[CSaleOrderUserProps](/api_help/sale/classes/csaleorderuserprops/index.php)

GetByID (доступен с 3.3.0)

GetByID
=======

Включить вкладки

Описание и параметры

Пример использования

### Описание и параметры

```
array
CSaleOrderUserProps::GetByID(
	int ID
);Копировать
```

Метод возвращает параметры профиля покупателя с кодом ID. Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | Код профиля покупателя. |

#### Возвращаемые значения

Возвращается ассоциативный массив параметров профиля покупателя с ключами:

| Ключ | Описание |
| --- | --- |
| ID | Код профиля покупателя. |
| NAME | Название профиля. |
| USER\_ID | Код пользователя, которому принадлежит профиль. |
| PERSON\_TYPE\_ID | Тип плательщика. |
| DATE\_UPDATE | Дата последнего изменения профиля. |

### Пример использования

```
<?
if ($ar = CSaleOrderUserProps::GetByID(12))
{
	echo "<pre>";
	print_r($ar);
	echo "</pre>";
}
?>Копировать
```

Новинки документации в соцсетях: