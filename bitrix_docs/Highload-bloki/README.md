# Структура документации Bitrix

> **О документации**  
Данная документация собрана с официального сайта Bitrix 20.04.25  

Полезные материалы, статьи и практические кейсы также доступны на моём сайте: [mosolovi.ru](https://mosolovi.ru)

## 📁 bitrix_docs 

```
+---ADLDAP_integratsija
¦       Sobytija.md

+---Biznes-protsessy
¦   ¦   Biznes-protsessy.md
¦   ¦   Biznes-protsessy_raw.html
¦   ¦   Biznes-protsessy_v_jadre_D7.md
¦   ¦   Dokument.md
¦   ¦   Interfejsy.md
¦   ¦   Klassy.md
¦   ¦   Servisy.md
¦   ¦   Sobytija.md
¦   ¦   
¦   +---Interfejsy
¦   ¦   ¦   IBPWorkflowDocument.md
¦   ¦   ¦   
¦   ¦   L---IBPWorkflowDocument
¦   ¦           CanUserOperateDocument.md
¦   ¦           CanUserOperateDocumentType.md
¦   ¦           CreateDocument.md
¦   ¦           DeleteDocument.md
¦   ¦           GetAllowableOperations.md
¦   ¦           GetAllowableUserGroups.md
¦   ¦           GetDocument.md
¦   ¦           GetDocumentAdminPage.md
¦   ¦           GetDocumentFields.md
¦   ¦           GetDocumentForHistory.md
¦   ¦           GetUsersFromUserGroup.md
¦   ¦           IsDocumentLocked.md
¦   ¦           LockDocument.md
¦   ¦           PublishDocument.md
¦   ¦           RecoverDocumentFromHistory.md
¦   ¦           UnlockDocument.md
¦   ¦           UnpublishDocument.md
¦   ¦           UpdateDocument.md
¦   ¦           
¦   L---Klassy
¦       ¦   CBPActivity.md
¦       ¦   CBPDocument.md
¦       ¦   CBPRuntime.md
¦       ¦   CBPWorkflow.md
¦       ¦   
¦       +---CBPActivity
¦       ¦       AddStatusChangeHandler.md
¦       ¦       Execute.md
¦       ¦       GetName.md
¦       ¦       GetRootActivity.md
¦       ¦       getTaskControls.md
¦       ¦       GetWorkflowInstanceId.md
¦       ¦       HandleFault.md
¦       ¦       Initialize.md
¦       ¦       RemoveStatusChangeHandler.md
¦       ¦       ShowTaskForm.md
¦       ¦       WriteToTrackingService.md
¦       ¦       
¦       +---CBPDocument
¦       ¦       AddDocumentToHistory.md
¦       ¦       AutoStartWorkflows.md
¦       ¦       CanOperate.md
¦       ¦       CanUserOperateDocument.md
¦       ¦       CanUserOperateDocumentType.md
¦       ¦       DeleteWorkflowTemplate.md
¦       ¦       GetAllowableEvents.md
¦       ¦       GetAllowableOperations.md
¦       ¦       GetDocumentState.md
¦       ¦       GetDocumentStates.md
¦       ¦       GetUserTasksForWorkflow.md
¦       ¦       GetWorkflowTemplatesForDocumentType.md
¦       ¦       OnDocumentDelete.md
¦       ¦       SendExternalEvent.md
¦       ¦       StartWorkflow.md
¦       ¦       TerminateWorkflow.md
¦       ¦       UpdateWorkflowTemplate.md
¦       ¦       
¦       +---CBPRuntime
¦       ¦       CreateWorkflow.md
¦       ¦       GetRuntime.md
¦       ¦       GetService.md
¦       ¦       GetWorkflow.md
¦       ¦       SendExternalEvent.md
¦       ¦       StartRuntime.md
¦       ¦       
¦       L---CBPWorkflow
¦               GetDocumentId.md
¦               GetExecutionResult.md
¦               GetExecutionStatus.md
¦               GetInstanceId.md
¦               GetRuntime.md
¦               GetService.md
¦               Konstruktor.md

+---Blogi
¦   ¦   Blogi.md
¦   ¦   Blogi_raw.html
¦   ¦   Blogi_v_jadre_D7.md
¦   ¦   Klassy.md
¦   ¦   Konstanty_modulja_blogov.md
¦   ¦   Sobytija.md
¦   ¦   Struktura_tablits_modulja_blogov.md
¦   ¦   
¦   +---Klassy
¦   ¦   ¦   blogTextParser.md
¦   ¦   ¦   CBlog.md
¦   ¦   ¦   CBlogCandidate.md
¦   ¦   ¦   CBlogCategory.md
¦   ¦   ¦   CBlogComment.md
¦   ¦   ¦   CBlogGroup.md
¦   ¦   ¦   CBlogImage.md
¦   ¦   ¦   CBlogPost.md
¦   ¦   ¦   CBlogSitePath.md
¦   ¦   ¦   CBlogTrackback.md
¦   ¦   ¦   CBlogUser.md
¦   ¦   ¦   CBlogUserGroup.md
¦   ¦   ¦   
¦   ¦   +---blogTextParser
¦   ¦   ¦       convert.md
¦   ¦   ¦       
¦   ¦   +---CBlog
¦   ¦   ¦       Add.md
¦   ¦   ¦       BuildRSS.md
¦   ¦   ¦       CanUserCreateBlog.md
¦   ¦   ¦       CanUserManageBlog.md
¦   ¦   ¦       Delete.md
¦   ¦   ¦       GetBlogUserCommentPerms.md
¦   ¦   ¦       GetBlogUserPostPerms.md
¦   ¦   ¦       GetByID.md
¦   ¦   ¦       GetByOwnerID.md
¦   ¦   ¦       GetList.md
¦   ¦   ¦       IsBlogOwner.md
¦   ¦   ¦       IsFriend.md
¦   ¦   ¦       PreparePath.md
¦   ¦   ¦       SetBlogPerms.md
¦   ¦   ¦       Update.md
¦   ¦   ¦       
¦   ¦   +---CBlogCandidate
¦   ¦   ¦       Add.md
¦   ¦   ¦       Delete.md
¦   ¦   ¦       GetByID.md
¦   ¦   ¦       GetList.md
¦   ¦   ¦       
¦   ¦   +---CBlogCategory
¦   ¦   ¦       Add.md
¦   ¦   ¦       Delete.md
¦   ¦   ¦       GetByID.md
¦   ¦   ¦       GetList.md
¦   ¦   ¦       Update.md
¦   ¦   ¦       
¦   ¦   +---CBlogComment
¦   ¦   ¦       Add.md
¦   ¦   ¦       Delete.md
¦   ¦   ¦       GetByID.md
¦   ¦   ¦       GetList.md
¦   ¦   ¦       Update.md
¦   ¦   ¦       
¦   ¦   +---CBlogGroup
¦   ¦   ¦       Add.md
¦   ¦   ¦       Delete.md
¦   ¦   ¦       GetByID.md
¦   ¦   ¦       GetList.md
¦   ¦   ¦       Update.md
¦   ¦   ¦       
¦   ¦   +---CBlogImage
¦   ¦   ¦       Add.md
¦   ¦   ¦       AddImageResizeHandler.md
¦   ¦   ¦       CheckFields.md
¦   ¦   ¦       Delete.md
¦   ¦   ¦       GetByID.md
¦   ¦   ¦       GetList.md
¦   ¦   ¦       ImageFixSize.md
¦   ¦   ¦       ImageResizeHandler.md
¦   ¦   ¦       Update.md
¦   ¦   ¦       
¦   ¦   +---CBlogPost
¦   ¦   ¦       Add.md
¦   ¦   ¦       CanUserDeletePost.md
¦   ¦   ¦       CanUserEditPost.md
¦   ¦   ¦       Delete.md
¦   ¦   ¦       GetBlogUserCommentPerms.md
¦   ¦   ¦       GetBlogUserPostPerms.md
¦   ¦   ¦       GetByID.md
¦   ¦   ¦       GetList.md
¦   ¦   ¦       GetListCalendar.md
¦   ¦   ¦       PreparePath.md
¦   ¦   ¦       SetPostPerms.md
¦   ¦   ¦       Update.md
¦   ¦   ¦       
¦   ¦   +---CBlogSitePath
¦   ¦   ¦       Add.md
¦   ¦   ¦       Delete.md
¦   ¦   ¦       GetByID.md
...
