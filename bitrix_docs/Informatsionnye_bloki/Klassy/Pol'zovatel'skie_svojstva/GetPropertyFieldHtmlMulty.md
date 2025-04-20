[Информационные блоки](/api_help/iblock/index.php)

[Классы](/api_help/iblock/classes/index.php)

[Пользовательские свойства](/api_help/iblock/classes/user_properties/index.php)

GetPropertyFieldHtmlMulty (доступен с 5.0.1)

GetPropertyFieldHtmlMulty
=========================

```
string
CIBlockProperty*::GetPropertyFieldHtmlMulty(
	arProperty,
	arValues,
	strHTMLControlName
);Копировать
```

Вывод формы редактирования множественного свойства. Если отсутствует, то используется [GetPropertyFieldHtml](/api_help/iblock/classes/user_properties/GetPropertyFieldHtml.php) для каждого значения отдельно (у множественных свойств). Метод статический при использовании штатных свойств. У свойств, созданных клиентом, обязан быть статическим при использовании php7.

#### Параметры вызова

| Параметр | Описание |
| --- | --- |
| arProperty | Метаданные свойства. См. [Свойства элементов инфоблока](/api_help/iblock/fields.php#fproperty) |
| value | Значение свойства. Массив вида:  ``` array(  	"VALUE" => значение,  	"DESCRIPTION" => описание,  );Копировать ``` |
| strHTMLControlName | Имена элементов управления для заполнения значения свойства и его описания. Массив вида:  ``` array(  	"VALUE" => html //безопасное имя для значения,  	"DESCRIPTION" => //html безопасное имя для описания,  	"MODE" => //может принимать зачение "FORM_FILL" при вызове из формы редактирования элемента  		//или "iblock_element_admin" при редактировании в режиме просмотра списка элементов,  		//а также "EDIT_FORM" при редактировании инфоблока.  	"FORM_NAME" => //имя формы в которую будет встроен элемент управления.  );Копировать ``` |

#### Возвращаемое значение

Возвращаемое значение - html-код.

Новинки документации в соцсетях: