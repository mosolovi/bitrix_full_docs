[Подписка, рассылки](/api_help/subscribe/index.php)

[Классы](/api_help/subscribe/classes/index.php)

[CPostingGeneral](/api_help/subscribe/classes/cpostinggeneral/index.php)

Класс CPostingGeneral (с версии 3.1.1)

Класс CPostingGeneral
=====================

**CPostingGeneral** - класс для работы с выпусками новостей подписки.

#### Методы класса

| Метод | Описание | С версии |
| --- | --- | --- |
| [Add](/api_help/subscribe/classes/cpostinggeneral/cpostingadd.php) | Метод добавляет выпуск. | 3.1.1 |
| [Delete](/api_help/subscribe/classes/cpostinggeneral/cpostingdelete.php) | Метод удаляет выпуск по его идентификатору. | 3.1.1 |
| [GetByID](/api_help/subscribe/classes/cpostinggeneral/cpostinggetbyid.php) | Метод возвращает выпуск по его идентификатору. | 3.1.1 |
| [GetEmails](/api_help/subscribe/classes/cpostinggeneral/cpostinggetemails.php) | Метод возвращает массив адресов, по которым выпуск будет отправлен. | 3.3.2 |
| [GetGroupList](/api_help/subscribe/classes/cpostinggeneral/cpostinggetgrouplist.php) | Метод возвращает выборку групп пользователей, на которые будет отправлен выпуск. | 3.1.1 |
| [UpdateGroups](/api_help/subscribe/classes/cpostinggeneral/cpostingupdategroups.php) | Метод изменяет информацию о привязке выпуска к группам пользователей. | 3.1.1 |
| [GetRubricList](/api_help/subscribe/classes/cpostinggeneral/cpostinggetrubriclist.php) | Метод возвращает выборку рассылок, на которые будет отправлен выпуск. | 3.1.1 |
| [UpdateRubrics](/api_help/subscribe/classes/cpostinggeneral/cpostingupdaterubrics.php) | Метод изменяет информацию о привязке выпуска к рубрикам подписки. | 3.1.1 |
| [SendMessage](/api_help/subscribe/classes/cpostinggeneral/cpostingsendmessage.php) | Метод возвращает true при успешной отправке, false при неуспешной, "CONTINUE" при частичной отправке. При неуспешной отправке переменная LAST\_ERROR класса содержит сообщение об ошибке. | 3.2.0 |
| [Update](/api_help/subscribe/classes/cpostinggeneral/cpostingupdate.php) | Метод изменяет информацию о выпуске по его идентификатору. | 3.1.1 |
| [SaveFile](/api_help/subscribe/classes/cpostinggeneral/cpostingsavefile.php) | Метод добавляет вложение к выпуску сохраняя и регистрируя его в таблице файлов (b\_file). | 4.0.5 |
| [DeleteFile](/api_help/subscribe/classes/cpostinggeneral/cpostingdeletefile.php) | Метод удаляет одно или все вложения выпуска. | 4.0.5 |
| [GetFileList](/api_help/subscribe/classes/cpostinggeneral/cpostinggetfilelist.php) | Метод возвращает выборку вложений выпуска. | 4.0.5 |
| [AutoSend](/api_help/subscribe/classes/cpostinggeneral/cpostingautosend.php) | Метод для отправки выпуска с помощью cron'а или агента. | 4.0.5 |
| [ChangeStatus](/api_help/subscribe/classes/cpostinggeneral/cpostingchangestatus.php) | Метод изменяет статус выпуска. | 4.0.5 |
| [GetEmailStatuses](/api_help/subscribe/classes/cpostinggeneral/GetEmailStatuses.php) | Метод возвращает массив статусов в очереди выпуска на отправку. | 8.5.3 |
| [GetEmailsByStatus](/api_help/subscribe/classes/cpostinggeneral/GetEmailsByStatus.php) | Метод возвращает выборку из очереди на отправку. | 8.5.3 |

Новинки документации в соцсетях: