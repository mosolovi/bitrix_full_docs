[Подписка, рассылки](/api_help/subscribe/index.php)

[Классы](/api_help/subscribe/classes/index.php)

[CRubric](/api_help/subscribe/classes/crubric/index.php)

Update (доступен с 5.0.2)

Update
======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
bool
CRubric::Update(
	int ID,
	array arFields
);Копировать
```

Метод модифицирует рассылку. Метод нестатический.

#### Параметры

| Параметр | Описание | С версии |
| --- | --- | --- |
| ID | Идентификатор рассылки. |  |
| arFields | Массив со значениями [полей объекта "Рассылка"](/api_help/subscribe/classes/crubric/crubric.fields.php). |  |

#### Возвращаемые значения

В случае успешного изменения возвращается true. В противном случает возвращается false,
и переменная класса LAST\_ERROR содержит сообщение об ошибке.

### Примеры использования

```
$rubric = new CRubric;
$arFields = Array(
	"ACTIVE" => ($ACTIVE <> "Y"? "N":"Y"),
	"NAME" => $NAME,
	"SORT" => $SORT,
	"DESCRIPTION" => $DESCRIPTION,
	"LID" => $LID
);
if($ID>0)
{
	if(!$rubric->Update($ID, $arFields))
		echo $rubric->LAST_ERROR;
}Копировать
```

Новинки документации в соцсетях: