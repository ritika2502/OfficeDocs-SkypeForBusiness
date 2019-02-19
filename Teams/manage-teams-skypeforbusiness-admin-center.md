---
title: Manage Teams during the transition to the new Microsoft Teams admin center
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/05/2018
ms.topic: article
ms.service: msteams
ms.reviewer: 
search.appverid: MET150
description: Understand how to manage tenant-wide and user settings for Teams during the transition from the Teams experience in the Office 365 admin center to the new Microsoft Teams admin center.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto: 
- Microsoft Teams
- Skype for Business Online
---

Manage Teams during the transition to the new Microsoft Teams admin center
======================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## What is the new Microsoft Teams admin center?  

The new admin center experience will provide you with a unified experience to manage both Teams and Skype for Business. We’re delivering additional functionality, end-to-end insights, and the ability to manage Teams settings on a user level.

![Screenshot of the Microsoft Teams admin center.](media/manage-teams-skype-for-business-admin-center-portal.png)

## Settings migrated to the new Microsoft Teams admin center

The following table identifies the sections of the Teams experience that have been migrated and shows the relationship between the current settings and the policies in the new admin portal.

|Section of Teams in Office 365 admin center  |Setting name (Tenant level)  |Microsoft Teams admin center policy   |Level: Tenant or User   |
|---------|---------|---------|---------|
|General     |Show Organizational Chat in Personal Profile        |  [TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)       |  Tenant       |
|General     |Use Skype for Business for recipients who don’t have Teams         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Tenant         |
|Email integration     |Allow users to send emails to channels         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Tenant         |
|Email integration     |Allow senders list         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)        |Tenant         |
|Custom cloud storage     |Box         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Tenant         |
|Custom cloud storage     |Dropbox        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Tenant         |
|Custom cloud storage     |Google Drive        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Tenant         |
|Custom cloud storage     |ShareFile        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Tenant         |
|Settings by user/license type     |Turn Microsoft Teams on or off for all users          |Deprecated<sup>1</sup>        |         |
|Teams and channels     |         |Redirects to Azure Active Directory Group Management (same as current experience).              |User         |
|Teams and channels     |         |Redirects to AAD Group Management (same as current experience).             |User          |
|Calls and Meetings     |Allow scheduling for private meetings         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |User          |
|Calls and Meetings     |Allow Ad-hoc channel meetup         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |User          |
|Calls and Meetings     |Allow scheduling for channel meetings         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |User          |
|Calls and Meetings     |Allow videos in meetings         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |User          |
|Calls and Meetings     |Allow screen sharing in meetings         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |User          |
|Calls and Meetings     |Allow private calling         |[TeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)        |User          |
|Messaging     |Enable Giphy so users can add gifs to conversations         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |User         |
|Messaging     |Content rating         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |User         |
|Messaging     |Enable memes that users can edit and add to conversations         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |User         |
|Messaging     |Enable stickers that users can edit and add to conversations         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |User         |
|Messaging     |Allow owners to delete all messages         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |User         |
|Messaging     |Allow users to edit their own messages         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |User         |
|Messaging     |Allow users to delete their own messages         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |User         |
|Messaging     |Allows users to chat privately         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |User         |
|Apps     |Default Apps*<sup>1</sup>         |[Org wide app settings]         |Tenant         |
|Apps     |Allow external apps      |[Org wide app settings]         |Tenant         |
|Apps     |Enable new external apps by default   |[Org wide App Settings]         |Tenant         |
|Apps     |Allow sideloading of external apps     |[TeamsAppSetupPolicy]         |User         |

<sup>1</sup> Deprecated for Guest. Enabling/disabling Guest can now be managed in the Microsoft Teams admin center. Enabling/disabling Teams for Business Enterprise, Edu Student, and Edu Faculty will be deprecated soon. This should be managed by assigning licenses in the Office 365 admin center. See [Manage user access to Microsoft Teams](user-access.md).

<sup>2</sup> The existing tenant level configurations for default apps would be migrated to org wide settings, but admins can leverage the TeamsAppPermissionPolicy to manage enable/disable of apps at a user level

> [!NOTE]
> You’ll continue to use the Groups dashboard in the Office 365 admin center for configuration related to Teams and channels. Settings for Apps will remain in the Teams area of the Office 365 admin center and will be migrated later. 

## Manage settings during the migration

You can continue to modify settings in the Office 365 admin center and the Skype for Business admin center until migration for a section is complete for your tenant. 

The following table shows where you can manage features during the migration.

|Feature  |Microsoft Teams admin center                      |Skype for Business admin center (legacy)  |Office 365 admin center  |
|---------|:---------:|:---------:|:---------:|
|Teams Messaging, Meetings, and Live Events policies     |     X    |         |         |
|Teams Upgrade policy     |    X     |         |         |
|Guest settings for Messaging, Meetings, and Voice     |   X      |         |         |
|Teams Lifecycle Management   |    X    |      |       |
|Teams Settings   |    X    |      |       |
|External access settings     |    X    |      |       |
|User management    |         |         |    X     |    
|Audio conferencing     |    X     |    X     |         |
|Calling plans     |         |    X     |         |
|Phone System    |         |     X    |         |
|Phone number management     |         |   X      |         |
|Licensing for Cloud voice features     |         |         |    X     |
|Auto attendants     |         |    X     |         |
|Call queues     |         |    X     |         |

## Manage settings after the migration

When the migration of these settings is complete, we’ll disable them in the Office 365 admin center and the Skype for Business admin center, and they can then be managed in the new Microsoft Teams admin center.


