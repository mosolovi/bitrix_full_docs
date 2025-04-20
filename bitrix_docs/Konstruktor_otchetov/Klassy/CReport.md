[Конструктор отчетов](/api_help/report/index.php)

[Классы](/api_help/report/classes/index.php)

CReport (с версии 11.0.0)

CReport
=======

**CReport** - класс для манипуляций с отчётами.

| Класс | Описание | С версии |
| --- | --- | --- |
| [Update](/api_help/report/classes/creport/update.php) | Изменяет существующий отчёт. |  |
| [Add](/api_help/report/classes/creport/add.php) | Добавляет новый отчёт. |  |
| [GetList](/api_help/report/classes/creport/getlist.php) | Добавляет новый отчёт. | 14.1.1 |
| [Delete](/api_help/report/classes/creport/delete.php) | Удаляет существующий отчёт. | 14.1.1 |
| [setViewParams](/api_help/report/classes/creport/setviewparams.php) | Сохраняет параметры просмотра отчёта текущего пользователя. | 14.1.1 |
| [getViewParams](/api_help/report/classes/creport/getviewparams.php) | Позволяет получить параметры просмотра отчёта текущего пользователя. | 14.1.1 |
| [generateChains](/api_help/report/classes/creport/generatechains.php) | Формирует дерево объектов с полным набором всех полей, необходимых для формирования запроса выборки данных для каждого доступного поля отчёта. | 14.1.1 |
| [generateColumnTree](/api_help/report/classes/creport/generatecolumntree.php) | Формирует дерево с описанием доступных в отчёте полей с привязками к цепочкам сущностей. | 14.1.1 |
| [clearViewParams](/api_help/report/classes/creport/clearviewparams.php) | Очищает все сохранённые параметры просмотра отчёта с идентификатором `id` для текущего пользователя. | 14.1.1 |
| [attachLangToColumnTree](/api_help/report/classes/creport/attachlangtocolumntree.php) | Загружает языковые фразы для полей отчёта, используя описания сущностей и вспомогательный класс отчёта. | 14.1.1 |
| [fillFilterReferenceColumns](/api_help/report/classes/creport/fillfilterreferencecolumns.php) | Проверяет, с использованием метода [fillFilterReferenceColumn](/api_help/report/classes/creport/fillfilterreferencecolumns.php) вспомогательного класса, корректность значений фильтров, ссылающихся на сущности. | 14.1.1 |
| [GetCountInt](/api_help/report/classes/creport/getcountint.php) | Позволяет получить количество отчётов пользователя, соответствующих `ownerId`, или всех отчётов пользователя, если не указан `ownerId`. | 14.1.1 |
| [getFullColumnTitle](/api_help/report/classes/creport/getfullcolumntitle.php) | Дополняет название колонки отчёта суффиксами соответствующими настройкам этой колонки. | 14.1.1 |
| [prepareSelectViewElement](/api_help/report/classes/creport/prepareselectviewelement.php) | Формирует алиас и выражение для поля, учитывая опции, выбранные для него в настройках отчёта. | 14.1.1 |
| [isColumnPercentable](/api_help/report/classes/creport/columnpercentable.php) | Определяет, может ли вычисляться процент от заданной колонки отчёта. | 14.1.1 |
| [rewriteUserShortName](/api_help/report/classes/creport/rewriteusershortname.php) | Преобразует поля с составными именами пользователей в вычисляемые на уровне базы данных и возвращающие имена в заданном формате. | 14.1.1 |
| [generateValueUrl](/api_help/report/classes/creport/generatevalueurl.php) | Формирует ссылки, отображаемые в отчёте, на основе шаблонов, сформированных методом [appendHrefSelectElements](/api_help/report/classes/creport/appendhrefselectelements.php), и данных конкретных значений. | 14.1.1 |
| [appendHrefSelectElements](/api_help/report/classes/creport/appendhrefselectelements.php) | Добавляет информацию, необходимую для построения ссылок для значений, отображаемых в отчёте. | 14.1.1 |
| [getUniqueFieldsByTree](/api_help/report/classes/creport/getuniquefieldsbytree.php) | Формирует полный список доступных в отчёте полей из основной и связанных сущностей на основе информации, возвращаемой методом [generateColumnTree](/api_help/report/classes/creport/generatecolumntree.php). | 14.1.1 |
| [isValidFilterCompareVariation](/api_help/report/classes/creport/isvalidfiltercomparevariation.php) | Проверяет применимость операции сравнения к полю отчёта в фильтре. | 14.1.1 |
| [addFreshDefaultReports](/api_help/report/classes/creport/addfreshdefaultreports.php) | Добавляет отчёты по умолчанию. | 14.1.1 |
| [isColumnTotalCountable](/api_help/report/classes/creport/iscolumntotalcountable.php) | Определяет, может ли вычисляться итоговое значение для заданной колонки отчёта. | 14.1.1 |
| [sqlizeFilter](/api_help/report/classes/creport/sqlizefilter.php) | Преобразует фильтр из внутреннего формата модуля отчётов в представление, подходяещее для использования в методе *setFilter* класса *\Bitrix\Main\Entity\Query* с сохранением древовидной структуры фильтра. | 14.1.1 |
| [makeSingleFilter](/api_help/report/classes/creport/makesinglefilter.php) | Преобразует фильтр из внутреннего формата модуля отчётов в представление, подходящее для использования в методе *setFilter* класса *\Bitrix\Main\Entity\Query* с преобразованием древовидной структуры в последовательную. | 14.1.1 |
| [collectFullHumanTitles](/api_help/report/classes/creport/collectfullhumantitles.php) | Формирует массив названий для всех доступных полей отчёта на основе информации, возвращаемой методом [generateColumnTree](/api_help/report/classes/creport/generatecolumntree.php). | 14.1.1 |
| [getFormattedNameExpr](/api_help/report/classes/creport/getformattednameexpr.php) | Формирует выражение вычисляемого поля для метода [rewriteUserShortName](/api_help/report/classes/creport/rewriteusershortname.php) в соответствии с заданным форматом имени пользователя. | 14.1.1 |

Новинки документации в соцсетях: