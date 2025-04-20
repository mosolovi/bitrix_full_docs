[Задачи](/api_help/tasks/index.php)

[Константы](/api_help/tasks/constants/index.php)

Список констант

Список констант
===============

Включить вкладки

Константы CTasks

Константы CTaskItem

Константы CTaskFilterCtrl

### Константы CTasks

#### Статусы

| Константа | Описание | Числовые значения |
| --- | --- | --- |
| CTasks::METASTATE\_VIRGIN\_NEW | Новая задача (не просмотрена). | -2 |
| CTasks::METASTATE\_EXPIRED | Задача просрочена. | -1 |
| CTasks::METASTATE\_EXPIRED\_SOON | Задача почти просрочена. | -3 |
| CTasks::STATE\_NEW | Новая задача. (Не используется) | 1 |
| CTasks::STATE\_PENDING | Задача принята исполнителем. (Не используется) | 2 |
| CTasks::STATE\_IN\_PROGRESS | Задача выполняется. | 3 |
| CTasks::STATE\_SUPPOSEDLY\_COMPLETED | Условно завершена (ждет контроля постановщиком). | 4 |
| CTasks::STATE\_COMPLETED | Задача завершена. | 5 |
| CTasks::STATE\_DEFERRED | Задача отложена. | 6 |
| CTasks::STATE\_DECLINED | Задача отклонена исполнителем. (Не используется) | 7 |

#### Приоритеты

| Константа | Описание |
| --- | --- |
| CTasks::PRIORITY\_LOW | Низкий приоритет. |
| CTasks::PRIORITY\_AVERAGE | Нормальный приоритет. |
| CTasks::PRIORITY\_HIGH | Высокий приоритет. |

### Константы CTaskItem

#### Действия над задачей (для проверки прав)

| Константа | Описание |
| --- | --- |
| CTaskItem::ACTION\_ACCEPT | Принятие задачи (смена статуса в **CTasks::STATE\_PENDING**). |
| CTaskItem::ACTION\_DECLINE | Отклонение задачи (смена статуса в **CTasks::STATE\_DECLINED**). |
| CTaskItem::ACTION\_COMPLETE | Завершение задачи (смена статуса в **CTasks::STATE\_COMPLETED**, либо в **CTasks::STATE\_SUPPOSEDLY\_COMPLETED** — если постановщиком затребован контроль задачи и завершает задачу не постановщик). |
| CTaskItem::ACTION\_APPROVE | Одобрение задачи, требующей контроля (перевод из статуса **CTasks::STATE\_SUPPOSEDLY\_COMPLETED** в **CTasks::STATE\_COMPLETED**). |
| CTaskItem::ACTION\_DISAPPROVE | Возврат в работу задачи, требующей контроля (перевод из статуса **CTasks::STATE\_SUPPOSEDLY\_COMPLETED** в **CTasks::STATE\_NEW** или **CTasks::STATE\_PENDING**, если исполнитель является подчиненным постановщика). |
| CTaskItem::ACTION\_START | Перевод задачи в статус "выполняется" (**CTasks::STATE\_IN\_PROGRESS**). |
| CTaskItem::ACTION\_DELEGATE | Делегирование задачи подчиненному. |
| CTaskItem::ACTION\_REMOVE | Удаление задачи. |
| CTaskItem::ACTION\_EDIT | Редактирование задачи. |
| CTaskItem::ACTION\_DEFER | Откладывание задачи на потом (перевод в статус **CTasks::STATE\_DEFERRED**). |
| CTaskItem::ACTION\_RENEW | Возврат задачи в статус "Новая" (**CTasks::STATE\_NEW**) или "Принята" (**CTasks::STATE\_PENDING**, если исполнитель является подчиненным постановщика). |
| CTaskItem::ACTION\_CREATE | Создание задачи. |
| CTaskItem::ACTION\_CHANGE\_DEADLINE | Смена крайнего срока у задачи. |

#### Роли пользователя в задаче (для проверки прав)

| Константа | Описание |
| --- | --- |
| CTaskItem::ROLE\_NOT\_A\_MEMBER | Не является участником задачи. |
| CTaskItem::ROLE\_DIRECTOR | Постановщик. |
| CTaskItem::ROLE\_RESPONSIBLE | Исполнитель. |
| CTaskItem::ROLE\_ACCOMPLICE | Соисполнитель. |
| CTaskItem::ROLE\_AUDITOR | Наблюдатель. |

#### Формат описания (при получении описания задачи)

| Константа | Описание |
| --- | --- |
| CTaskItem::DESCR\_FORMAT\_RAW | Формат "как есть" - может быть HTML и BBCode, в зависимости от задачи. |
| CTaskItem::DESCR\_FORMAT\_HTML | Формат HTML. Если описание задачи в формате BBCode, то оно будет автоматически преобразовано в HTML. Если оно уже в формате HTML, то будет применен санитайзер в соответствии с настройками в модуле задач. |
| CTaskItem::DESCR\_FORMAT\_PLAIN\_TEXT | Формат "только текст". Все HTML/BB теги будут вырезаны. |

### Константы CTaskFilterCtrl

#### Идентификаторы предустановленных наборов фильтров

| Константа | Описание |
| --- | --- |
| CTaskFilterCtrl::ROOT\_PRESET | Псевдонабор, не содержит условия. Является родительским элементов для всех остальных наборов. |
| CTaskFilterCtrl::STD\_PRESET\_ACTIVE\_MY\_TASKS | "Мои задачи". |
| CTaskFilterCtrl::STD\_PRESET\_ACTIVE\_I\_AM\_DOER | "Поставленные мне". |
| CTaskFilterCtrl::STD\_PRESET\_ACTIVE\_I\_AM\_ORIGINATOR | "Созданные мной". |
| CTaskFilterCtrl::STD\_PRESET\_ACTIVE\_I\_AM\_AUDITOR | "Наблюдаемые". |
| CTaskFilterCtrl::STD\_PRESET\_DEFERRED\_MY\_TASKS | "Отложенные". |
| CTaskFilterCtrl::STD\_PRESET\_COMPLETED\_MY\_TASKS | "Завершенные". |
| CTaskFilterCtrl::STD\_PRESET\_ACTIVE\_I\_AM\_RESPONSIBLE | "Я исполнитель". |
| CTaskFilterCtrl::STD\_PRESET\_ACTIVE\_I\_AM\_ACCOMPLICE | "Я соисполнитель". |
| CTaskFilterCtrl::STD\_PRESET\_ALL\_MY\_TASKS | "Все". |
| CTaskFilterCtrl::STD\_PRESET\_ALIAS\_TO\_DEFAULT | Это синоним для **CTaskFilterCtrl::STD\_PRESET\_ACTIVE\_MY\_TASKS**. |

Новинки документации в соцсетях: