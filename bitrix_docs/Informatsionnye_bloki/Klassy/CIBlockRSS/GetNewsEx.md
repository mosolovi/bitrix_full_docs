[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[CIBlockRSS](/api_help/iblock/classes/ciblockrss/index.php)

GetNewsEx (доступен с 3.1.2)

GetNewsEx
=========

Включить вкладки

Описание и параметры

Смотрите также

Примеры использования

### Описание и параметры

```
array
CIBlockRSS::GetNewsEx(
	string SITE,
	string PORT,
	string PATH,
	string QUERY_STR,
	bool bOutChannel = false
);Копировать
```

Загружает xml c указанного адреса и разбирает его в массив. В качестве значения user-agent'а используется "BitrixSMRSS". После загрузки xml будет конвертирован в кодировку текущего сайта. Если во время работы метода возникли ошибки, то массив результата будет пустым. Нестатический метод.

**Примечание**: xml кешируется на время указанное в элементе ttl или если время не указано, то на один час.

#### Параметры вызова

| Параметр | Описание | С версии |
| --- | --- | --- |
| SITE | IP-адрес или доменное имя сайта. |  |
| PORT | Номер порта, к которому будет выполнено подключение. HTTP порт по умолчанию -  80. |  |
| PATH и QUERY\_STR | Объединяются через знак вопроса ("?") и передаются HTTP команде GET. |  |
| *bOutChannel* | Требуется указать true, если новости находятся вне элемента channel. | 3.2.1 |

#### Возвращаемое значение

Массив представления xml.

### Смотрите также

* [CIBlockRSS::](/api_help/iblock/classes/ciblockrss/index.php)[FormatArray](/api_help/iblock/classes/ciblockrss/formatarray.php)

### Примеры использования

```
<?
$arRSS = CIBlockRSS::GetNewsEx('www.1c-bitrix.ru', '80', '/bitrix/rss.php', 'ID=news_sm&LANG=ru&TYPE=news&LIMIT=5');
print_r($arRSS);
?>Копировать
```

Новинки документации в соцсетях: