[Интернет-магазин](/api_help/sale/index.php)

[Взаимодействие УС с сайтом](/api_help/sale/algorithms/index.php)

Алгоритм выгрузки данных на сайт

Алгоритм выгрузки данных на сайт
================================

Включить вкладки

Схема

Авторизация на сайте

Инициализация на сайте

Выгрузка файлов на сайт

Ожидание окончания обработки данных на сайте

Примечание

### Схема

Процесс выгрузки данных из учетной системы на сайт можно представить в виде следующей схемы:

![](/upload/api_help/sale/data_2_site.png)

### Авторизация на сайте

На этапе **Авторизация на сайте** учетная система получает ресурс из указанного адреса. Адрес генерируется по следующему формату: `<Адрес_скрипта> + "?type=" + <Тип_соединения> + "&mode=checkauth"`, где:

* **<Тип\_соединения>** может принимать значения **catalog** или **sale** в зависимости от того, что нужно выгружать (**sale** используется для выгрузки документов);
* **<Адрес\_скрипта>** - адрес, указанный в настройке обмена.

При успешной авторизации сайт возвращает временный файл с данными:

* во 2-ой строке содержится имя куки файла;
* в 3-ей строке содержится значение куки файла;
* в 4-ой строке содержится ключ сессии обмена (CSRF);
* в 5-ой строке содержится дата и время сервера сайта (CSRF).

### Инициализация на сайте

На этапе **Инициализация на сайте** учетная система получает ресурс из указанного адреса, а также сообщает о версии CommerceML. Адрес генерируется по следующему формату: `<Адрес_скрипта> + "?type=" + <Тип_соединения> + "&mode=init" + "&" + <Ключ_сессии> + "&version=" + <Версия_CommerceML>`, где:

* **<Тип\_соединения>** может принимать значения **catalog** или **sale** в зависимости от того, что нужно выгружать;
* **<Адрес\_скрипта>** - адрес, указанный в настройке обмена;
* **<Ключ\_сессии>** - ключ сессии, полученный на этапе **Авторизация на сайте**;
* **<Версия\_CommerceML>** - версия структуры XML-файлов обмена. Текущая версия - 3.1. Если не указать версию, то будут возвращены файлы версии 2.1.

Заголовок запроса формируется по следующему алгоритму: `"Cookie: " + КукиИмя + "=" + КукиЗначение`, где вся информация о куки берется с этапа **Авторизация на сайте**.

При успешной инициализации возвращает временный файл с данными:

* в 1-ой строке содержится признак, разрешен ли Zip (**zip=yes**);
* во 2-ой строке содержится информация об ограничении файлов по размеру (**file\_limit=**);
* в 3-ейй строке содержится ключ сессии обмена (**sessid=**);
* в 4-ой строке содержится версия CommerceML (**version=**).

### Выгрузка файлов на сайт

На этапе **Выгрузка файлов на сайт** учетная система отсылает сформированные и разбитые файлы XML в заданный адрес. Адрес генерируется по следующему формату: `<Адрес_скрипта> + "?type=" + <Тип_cоединения> + "&mode=file&filename=" + <имя_файла> +" &" + <Ключ_сессии>`, где:

* **<Тип\_соединения>** может принимать значения **catalog** или **sale** в зависимости от того, что нужно выгружать;
* **<Адрес\_скрипта>** - адрес, указанный в настройке обмена;
* **<Ключ\_сессии>** - ключ сессии, полученный на этапе **Авторизация на сайте**.

Заголовок запроса формируется по следующему алгоритму: `"Cookie: " + КукиИмя + "=" + КукиЗначение`, где вся информация о куки берется с этапа **Авторизация на сайте**.

Сайт может вернуть ответ:

* **success** - файл доставлен;
* **failure** - файл не доставлен;
* если ничего не пришло, то файл также не доставлен.

### Ожидание окончания обработки данных на сайте

На этапе **Ожидание окончания обработки данных на сайте** учетная система проверяет обработал ли сайт данные. Мониторится каждый выгруженный файл из учетной системы до тех пор, пока не будет получен ответ об успешном завершении обработки файла, неудачном завершении или ответ не будет получен вовсе. Адрес генерируется по следующему формату: `<Адрес_скрипта> + "?type=" + <Тип_cоединения> + "&mode=import&filename="+ <имя_файла> +" &" + <Ключ_сессии>`, где:

* **<Тип\_соединения>** может принимать значения **catalog** или **sale** в зависимости от того, что нужно выгружать;
* **<Адрес\_скрипта>** - адрес, указанный в настройке обмена;
* **<Ключ\_сессии>** - ключ сессии, полученный на этапе **Авторизация на сайте**.

Сайт может вернуть ответ, в котором в первой строке может содержаться:

* **progress** - файл обрабатывается (на следующей строке ответа указано на каком этапе);
* **success** - файл успешно обработан;
* **failure** - файл не обработан;
* если ничего не пришло, то файл также не обработан.

### Примечание

**Важно!** Если происходит **полная выгрузка**, то после успешной выгрузки информации о товарах, происходит деактивация незагруженных товаров и всей информации по ним. Деактивируются все элементы, дата модификации которых меньше даты выгрузки. Дата выгрузки берется из первой авторизации на сайте (первого пакета информации о товарах): `<Адрес_скрипта> + ?type=catalog&mode=deactivate +" ×tamp="" + <Дата_и_время_сервера_в_формате_timestamp> +" &" + <Ключ_сессии>`, где:

* **<Адрес\_скрипта>** - адрес, указанный в настройке обмена;
* **<Ключ\_сессии>** - ключ сессии, полученный на этапе **Авторизация на сайте**;
* **<Дата\_и\_время\_сервера>** - дата и время сервера, когда была произведена первая авторизация. Все данные о товарах, дата модификации которых меньше этого параметра, будут деактивированы.

Новинки документации в соцсетях: