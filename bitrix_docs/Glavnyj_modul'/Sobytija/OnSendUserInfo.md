[Главный модуль](/api_help/main/index.php)

[События](/api_help/main/events/index.php)

OnSendUserInfo (с версии 4.0.6)

OnSendUserInfo
==============

Включить вкладки

Описание и параметры

Смотрите также

Пример функции-обработчика

### Описание и параметры

```
функция-обработчик(
	array &arParams
);Копировать
```

Событие "OnSendUserInfo" вызывается в методе [CUser::SendUserInfo](/api_help/main/reference/cuser/senduserinfo.php) и предназначено для возможности переопределения параметров для [отправки почтового события](/api_help/main/general/mailevents.php) USER\_INFO.

#### Параметры

| Параметр | Описание |
| --- | --- |
| *arParams* | Массив полей для проверки имени входа и пароля:  * **FIELDS** - Массив, содержащий набор полей вида Array("поле 1"=>"значение 1", ...). При отправке все поля передаются в обработку шаблона USER\_INFO. Содержит по умолчанию след. поля:  + "USER\_ID" - код пользователя, + "STATUS" - текст статуса активности, + "MESSAGE" - текст сообщения, + "LOGIN" - имя входа, + "CHECKWORD" - контрольная строка, + "NAME" - имя пользователя, + "LAST\_NAME" - фамилия, + "EMAIL" - E-Mail адрес  * **USER\_FIELDS** - Все [поля пользователя](/api_help/main/reference/cuser/index.php), информация о котором будет высылаться. * **SITE\_ID** - код сайта, используется для определения шаблона почтового события USER\_INFO. |

**Примечание**. Параметр данного обработчика и элементы массива **arParams** являются ссылками на исходные переменные. Поэтому если вы измените значение параметра внутри обработчика, это приведет к смене значения исходной переменной поступившей на вход функции-обработчика.

### Смотрите также

* [CUser::SendUserInfo](/api_help/main/reference/cuser/senduserinfo.php)
* [Почтовые события](/api_help/main/general/mailevents.php)
* [События](http://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=43&LESSON_ID=3493)

### Пример функции-обработчика

```
<? 
// файл /bitrix/php_interface/init.php 
AddEventHandler("main", "OnSendUserInfo", "MyOnSendUserInfoHandler"); 
public static function MyOnSendUserInfoHandler(&$arParams) 
{ 
	if(strlen($arParams['USER_FIELDS']['LAST_NAME'])<=0) 
		$arParams['FIELDS']['CUSTOM_NAME'] = $arParams['USER_FIELDS']['LAST_NAME']; 
	else 
		$arParams['FIELDS']['CUSTOM_NAME'] = $arParams['USER_FIELDS']['LOGIN']; 
	// теперь в шаблоне USER_INFO можно использовать макрос #CUSTOM_NAME# 
} 
?>Копировать
```

Новинки документации в соцсетях: