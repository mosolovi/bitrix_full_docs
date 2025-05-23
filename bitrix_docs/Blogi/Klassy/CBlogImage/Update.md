[Блоги](/api_help/blogs/index.php)

[Классы](/api_help/blogs/classes/index.php)

[CBlogImage](/api_help/blogs/classes/cblogimage/index.php)

Update

Update
======

Включить вкладки

Описание и параметры

Примеры использования

### Описание и параметры

```
int
CBlogImage::Update(
	int   ID
	array arFields
);Копировать
```

Метод изменяет изображение в блоге. Метод статический.

#### Параметры метода

| Параметр | Описание | С версии |
| --- | --- | --- |
| ID | Идентификатор изменяемого изображения. |  |
| arFields | Массив вида *array("поле"=>"значение")*.  * **ID** - идентификатор изображения; * **FILE\_ID** - идентификатор файла; * **BLOG\_ID** - идентификатор блога; * **POST\_ID** - идентификатор сообщения блога; * **USER\_ID** - идентификатор пользователя; * **TIMESTAMP\_X** - время создания сообщения; * **TITLE** - заголовок изображения; * **IMAGE\_SIZE** - размер изображения в байтах; * **IS\_COMMENT** - флаг, прикреплено ли изображение к комментарию; * **COMMENT\_ID** - идентификатор комментария, к которому прикреплено изображение. |  |

#### Возвращаемое значение

Метод возвращает идентификатор измененного изображения, если изменение параметров прошло успешно. При возникновении ошибки метод вернет *false*, а в исключениях будут содержаться ошибки.

### Примеры использования

Изменяем **TITLE** для изображения с идентификатором 14:

```
$res = CBlogImage::Update(
	14,
	array("TITLE" => "new image title")
);
if($res)
	echo 'Success';Копировать
```

Новинки документации в соцсетях: