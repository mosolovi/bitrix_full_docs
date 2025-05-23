[Интернет-магазин](/api_help/sale/index.php)

[Классы](/api_help/sale/classes/index.php)

[CSaleTax](/api_help/sale/classes/csaletax/index.php)

GetByID (доступен с 3.3.1)

GetByID
=======

Включить вкладки

Описание и параметры

Возвращаемые значения

Пример использования

### Описание и параметры

```
array
CSaleTax::GetByID(
	int ID
);Копировать
```

Метод возвращает параметры налога с кодом ID. Нестатический метод.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| ID | Код налога. |

### Возвращаемые значения

Возвращается ассоциативный массив параметров налога с ключами:

| Ключ | Описание |
| --- | --- |
| ID | Код налога. |
| LID | Сайт. |
| NAME | Название налога. |
| CODE | Символьный код налога. |
| DESCRIPTION | Описание налога. |
| TIMESTAMP\_X | Дата последнего изменения записи. |

### Пример использования

```
<?
// Выведем параметры налога с кодом $TAX_ID
if ($arTax = CSaleTax::GetByID($TAX_ID))
{
	echo "<pre>";
	print_r($arTax);
	echo "</pre>";
}
?>Копировать
```

Новинки документации в соцсетях: