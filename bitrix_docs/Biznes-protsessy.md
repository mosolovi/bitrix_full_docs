[Бизнес-процессы](/api_help/bizproc/index.php)

Для разработчика

Для разработчика
================

О значениях полей форм модуля смотрите в [пользовательской документации](http://dev.1c-bitrix.ru/user_help/service/bizproc/index.php).

О работе с модулем подробно можно узнать в статьях [helpdesk.bitrix24.ru](https://helpdesk.bitrix24.ru/section/56679/) и курсах [Администратор. модули](https://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=41&CHAPTER_ID=04549) и [Администратор сервиса Битрикс24 (коробочная версия)](https://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=48&CHAPTER_ID=04744). Также доступен отдельный курс [Бизнес-процессы](https://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=57), в котором рассматривается [разработка бизнес-процессов](https://dev.1c-bitrix.ru/learning/course/index.php?COURSE_ID=57&CHAPTER_ID=04567).

  

Перед использованием модуля необходимо проверить установлен ли он и подключить его при помощи конструкции:

```
<?    if(CModule::IncludeModule("bizproc"))
{  
	//здесь можно использовать функции и классы модуля
} 
?> 
Копировать
```

Новинки документации в соцсетях: