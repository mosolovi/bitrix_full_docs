[Информационные блоки](/api_help/iblock/index.php)

События

События
=======

**Внимание!** Если инфоблок участвует в документообороте, то событие будет вызываться дважды, на элемент и его копию. Чтобы избежать повторного вызова рекомендуется уже в событии проверять элемент и дальше либо обрабатывать его, либо нет. Проверять можно по полю [WF\_PARENT\_ELEMENT\_ID](/api_help/iblock/classes/ciblockelement/getlist.php).

В некоторых случаях (например, в событии **OnAfterIBlockElementAdd**) использовать это поле напрямую нельзя: поле элемента **WF\_PARENT\_ELEMENT\_ID** в обоих вызовах заполнено и равно одному и тому же ID. В этом случае необходимо сравнить **WF\_PARENT\_ELEMENT\_ID** с **ID** элемента и если они совпадают, то это и есть искомый элемент из двух.

| Событие | Вызывается | Метод | С версии |
| --- | --- | --- | --- |
| [OnBeforeIBlockAdd](/api_help/iblock/events/onbeforeiblockadd.php) | перед добавлением информационного блока. | CIBlock::CheckFields | 4.0.6 |
| [OnAfterIBlockAdd](/api_help/iblock/events/onafteriblockadd.php) | после добавления информационного блока. | [Add](/api_help/iblock/classes/ciblock/add.php) | 4.0.6 |
| [OnBeforeIBlockUpdate](/api_help/iblock/events/onbeforeiblockupdate.php) | перед изменением информационного блока. | CIBlock::CheckFields | 4.0.6 |
| [OnAfterIBlockUpdate](/api_help/iblock/events/onafteriblockupdate.php) | после изменения информационного блока. | [Update](/api_help/iblock/classes/ciblock/update.php) | 4.0.6 |
| [OnBeforeIBlockDelete](/api_help/iblock/events/onbeforeiblockdelete.php) | перед удалением информационного блока. | [Delete](/api_help/iblock/classes/ciblock/delete.php) | 3.3.8 |
| [OnIBlockDelete](/api_help/iblock/events/oniblockdelete.php) | при удалении информационного блока. | [Delete](/api_help/iblock/classes/ciblock/delete.php) | 3.2.1 |
| [OnBeforeIBlockPropertyAdd](/api_help/iblock/events/onbeforeiblockpropertyadd.php) | перед добавлением свойства. | CIBlockProperty::CheckFields | 4.0.6 |
| [OnAfterIBlockPropertyAdd](/api_help/iblock/events/onafteriblockpropertyadd.php) | после добавления свойства. | [Add](/api_help/iblock/classes/ciblockproperty/add.php) | 4.0.6 |
| [OnBeforeIBlockPropertyUpdate](/api_help/iblock/events/onbeforeiblockpropertyupdate.php) | перед изменением свойства. | CIBlockProperty::CheckFields | 4.0.6 |
| OnIBlockPropertyDelete | при удалении свойства. | [Delete](/api_help/iblock/classes/ciblockproperty/delete.php) | 4.0.6 |
| [OnAfterIBlockPropertyUpdate](/api_help/iblock/events/onafteriblockpropertyupdate.php) | после изменения свойства. | [Update](/api_help/iblock/classes/ciblockproperty/update.php) | 4.0.6 |
| [OnBeforeIBlockPropertyDelete](/api_help/iblock/events/onbeforeiblockpropertydelete.php) | перед удалением свойства. | [Delete](/api_help/iblock/classes/ciblockproperty/delete.php) | 4.0.6 |
| [OnIBlockPropertyBuildList](/api_help/iblock/events/OnIBlockPropertyBuildList.php) | при построении списка свойств. | [GetUserType](/api_help/iblock/classes/ciblockproperty/GetUserType.php) | 5.1.0 |
| [OnBeforeIBlockSectionAdd](/api_help/iblock/events/onbeforeiblocksectionadd.php) | перед добавлением раздела. | CIBlockSection::CheckFields | 4.0.6 |
| [OnAfterIBlockSectionAdd](/api_help/iblock/events/onafteriblocksectionadd.php) | после добавления раздела. | [Add](/api_help/iblock/classes/ciblocksection/add.php) | 4.0.6 |
| [OnBeforeIBlockSectionUpdate](/api_help/iblock/events/onbeforeiblocksectionupdate.php) | перед изменением раздела. | CIBlockSection::CheckFields | 4.0.6 |
| [OnAfterIBlockSectionUpdate](/api_help/iblock/events/onafteriblocksectionupdate.php) | после изменения раздела. | [Update](/api_help/iblock/classes/ciblocksection/update.php) | 4.0.6 |
| [OnBeforeIBlockSectionDelete](/api_help/iblock/events/onbeforeiblocksectiondelete.php) | перед удалением раздела. | [Delete](/api_help/iblock/classes/ciblocksection/delete.php) | 4.0.6 |
| OnAfterIBlockSectionDelete | после удаления раздела. | [Delete](/api_help/iblock/classes/ciblocksection/delete.php) | 7.0.3 |
| [OnBeforeIBlockElementAdd](/api_help/iblock/events/onbeforeiblockelementadd.php) | перед добавлением элемента. | CIBlockElement::CheckFields | 4.0.6 |
| [OnStartIBlockElementAdd](/api_help/iblock/events/OnStartIBlockElementAdd.php) | в момент начала добавления элемента. | CIBlockElement::CheckFields | 7.1.8 |
| [OnAfterIBlockElementAdd](/api_help/iblock/events/onafteriblockelementadd.php) | после добавления элемента. | [Add](/api_help/iblock/classes/ciblockelement/add.php) | 4.0.6 |
| [OnBeforeIBlockElementUpdate](/api_help/iblock/events/onbeforeiblockelementupdate.php) | перед изменением элемента. | CIBlockElement::CheckFields | 4.0.6 |
| [OnStartIBlockElementUpdate](/api_help/iblock/events/OnStartIBlockElementUpdate.php) | в момент начала изменения элемента. | CIBlockElement::CheckFields | 7.1.8 |
| [OnAfterIBlockElementUpdate](/api_help/iblock/events/onafteriblockelementupdate.php) | после изменения элемента. | [Update](/api_help/iblock/classes/ciblockelement/update.php) | 4.0.6 |
| [OnBeforeIBlockElementDelete](/api_help/iblock/events/onbeforeiblockelementdelete.php) | перед удалением элемента. | [Delete](/api_help/iblock/classes/ciblockelement/delete.php) | 4.0.6 |
| [OnAfterIBlockElementDelete](/api_help/iblock/events/onafteriblockelementdelete.php) | после удаления элемента. | [Delete](/api_help/iblock/classes/ciblockelement/delete.php) | 5.0.0 |
| [OnIBlockElementDelete](/api_help/iblock/events/oniblockelementdelete.php) | при удалении элемента информационного блока. | [Delete](/api_help/iblock/classes/ciblockelement/delete.php) | 3.1.3 |
| OnBeforeEventLog | перед внесением записи в лог. | [Update](/api_help/iblock/classes/ciblockelement/update.php) | 11.0.8 |
| OnSearchGetFileContent | при поиске файла. | CIBlockElement::\_\_GetFileContent | 7.1.1 |
| GetAuditTypesIblock | при возвращении описания журналу событий | CEventIBlock::GetAuditTypes | 11.0.0 |
| OnAdminSubContextMenuShow | аналог [OnAdminContextMenuShow](/api_help/main/events/onadmincontextmenushow.php) для списка SKU | CAdminSubContextMenu::Show | 11.0.12 |
| OnAdminSubListDisplay | аналог [OnAdminListDisplay](/api_help/main/events/onadminlistdisplay.php) для списка SKU | CAdminSubList::Display | 10.0.3 |
| [OnAfterIBlockElementSetPropertyValues](/api_help/iblock/events/onafteriblockelementsetpropertyvalues.php) | после сохранения значений всех свойств элемента методом [CIBlockElement::SetPropertyValues](/api_help/iblock/classes/ciblockelement/setpropertyvalues.php). | [CIBlockElement::SetPropertyValues](/api_help/iblock/classes/ciblockelement/setpropertyvalues.php) | 14.5.1 |
| [OnAfterIBlockElementSetPropertyValuesEx](/api_help/iblock/events/onafteriblockelementsetpropertyvaluesex.php) | после сохранения значений свойств элемента методом [CIBlockElement::SetPropertyValuesEx](/api_help/iblock/classes/ciblockelement/setpropertyvaluesex.php). | [CIBlockElement::SetPropertyValuesEx](/api_help/iblock/classes/ciblockelement/setpropertyvaluesex.php) | 14.5.1 |
| [OnIBlockElementAdd](/api_help/iblock/events/oniblockelementadd.php) | в момент добавления элемента информационного блока. | [CIBlockElement::Add](/api_help/iblock/classes/ciblockelement/add.php) | 15.5.12 |
| [OnIBlockElementUpdate](/api_help/iblock/events/oniblockelementupdate.php) | в момент изменения элемента информационного блока. | [CIBlockElement::Update](/api_help/iblock/classes/ciblockelement/update.php) | 15.5.12 |
| [OnIBlockElementSetPropertyValues](/api_help/iblock/events/oniblockelementsetpropertyvalues.php) | в момент сохранения значений свойств элемента инфоблока. | [CIBlockElement::SetPropertyValues](/api_help/iblock/classes/ciblockelement/setpropertyvalues.php) | 15.5.12 |
| [OnIBlockElementSetPropertyValuesEx](/api_help/iblock/events/oniblockelementsetpropertyvaluesex.php) | до внесения изменений в базу после валидации входящих данных. | [CIBlockElement::SetPropertyValuesEx](/api_help/iblock/classes/ciblockelement/setpropertyvaluesex.php) | 17.6.5 |

Новинки документации в соцсетях: