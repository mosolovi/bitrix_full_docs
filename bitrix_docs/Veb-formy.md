[Веб-формы](/api_help/form/index.php)

Для разработчиков

Для разработчиков
=================

Включить вкладки

Описание

Компоненты 2.0

### Описание

Данный раздел содержит информацию для веб-разработчиков, использующих модуль **Веб-формы** для решения задач, выходящих за рамки возможностей стандартных [компонентов](#components) модуля.

Модуль **Веб-формы** обеспечивает:

* Наглядный интерфейс создания [веб-форм](/api_help/form/terms.php#form), включающий в себя:
  + формирование списка [вопросов](/api_help/form/terms.php#question) и [ответов](/api_help/form/terms.php#answer) на них;
  + формирование списка дополнительных [полей](/api_help/form/terms.php#field);
  + формирование списка [статусов](/api_help/form/terms.php#status) [результатов](/api_help/form/terms.php#result) веб-формы;
  + распределение [прав доступа](/api_help/form/permissions.php) на веб-форму и каждый статус в отдельности.
* Вывод веб-формы для заполнения.
* [Сохранение](/api_help/form/classes/cformresult/add.php) значений ответов на вопросы веб-формы в виде результатов.
* Выполнение ряда вспомогательных действий в момент сохранения результата:
  + [проверка](/api_help/form/classes/cform/check.php) введенных данных на корректность;
  + [отсылка](/api_help/form/classes/cformresult/mail.php) данных результата посредством электронной почты;
  + [создание](/api_help/form/classes/cformresult/setevent.php) события в модуле Статистика.
* Вывод результатов в виде списка, а также возможность выполнения следующих действий:
  + редактирование и [обновление](/api_help/form/classes/cformresult/update.php) результата;
  + [смена статуса](/api_help/form/classes/cformresult/setstatus.php) результата;
  + [удаление](/api_help/form/classes/cformresult/delete.php) результата;
  + фильтрация результатов по настраиваемому набору [вопросов](/api_help/form/terms.php#question) и [полей](/api_help/form/terms.php#field).

Перед использованием модуля необходимо проверить установлен ли он и подключить его при помощи конструкции:

```
<?
if(CModule::IncludeModule("form"))
{  
	//здесь можно использовать функции и классы модуля
} 
?>Копировать
```

### Компоненты 2.0

  
Модуль включает в себя следующие Компоненты 2.0:
  


| **Компоненты модуля** | | |
| --- | --- | --- |
| **Название** | **Имя в пространстве имен bitrix** | **Описание** |
| [Веб-форма (комплексный компонент)](https://dev.1c-bitrix.ru/user_help/components/services/web_forms/form.php) | **form** | Компонент, создавая физически только одну страницу, позволяет получить несколько страниц: заполнение веб-формы, со списком результатов, редактирование результата, просмотр результата и т.д. |
| [Редактирование результата](https://dev.1c-bitrix.ru/user_help/components/services/web_forms/form_result_edit.php) | **form.result.edit** | Служит для редактирования результатов заполнения веб-форм. |
| [Список результатов](https://dev.1c-bitrix.ru/user_help/components/services/web_forms/form_result_list.php) | **form.result.list** | Предназначен для вывода списка результатов выбранной веб-формы. |
| [Список своих результатов](https://dev.1c-bitrix.ru/user_help/components/services/web_forms/form_result_list_my.php) | **form.result.list.my** | Выводит список своих результатов по нескольким формам. |
| [Заполнение веб-формы](https://dev.1c-bitrix.ru/user_help/components/services/web_forms/form_result_new.php) | **form.result.new** | Служит для вывода формы и добавления результата, т.е. для ее заполнения. |
| [Просмотр результата](https://dev.1c-bitrix.ru/user_help/components/services/web_forms/form_result_view.php) | **form.result.view** | Служит для просмотра результата заполнения веб-формы. |

Новинки документации в соцсетях: