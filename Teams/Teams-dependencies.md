---
title: Dependencias de Office 365 para Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
description: Microsoft Teams depende de los grupos de Office 365, SharePoint Online y OneDrive para la Empresa.
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: e04770535976f509a8ac16cf054ea5e6760b5231
ms.sourcegitcommit: f6c2673a2ccd951770296972234938e627bd49ad
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2017
---
<a name="office-365-dependencies-for-microsoft-teams"></a>Dependencias de Office 365 para Microsoft Teams
===========================================

Microsoft Teams depende de los grupos de Office 365 para almacenar las suscripciones de los equipos y otras propiedades como la configuración de clasificación de datos de los equipos. Grupos de Office 365 es un servicio que proporciona suscripciones entre aplicaciones para un conjunto de activos de grupo compartidos, como un sitio de SharePoint o un panel de Power BI. De esta manera, los equipos pueden colaborar de forma efectiva y segura. 

Teams también depende de SharePoint Online y OneDrive para la Empresa para almacenar archivos y documentos de canales y conversaciones de chat. Además, Teams depende de los grupos de Office 365 para almacenar las suscripciones de los equipos y otras propiedades como la configuración de clasificación de datos de los equipos. Los invitados están sujetos a los límites de servicio de [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) y [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).
  
    
    
Para habilitar toda la experiencia de acceso de invitado de Teams, los administradores de Office 365 tienen que seleccionar **Activado** en las siguientes opciones:
  
    
    

- En SharePoint Online: **Only allow sharing with external users already in the directory** (Permitir solo compartir con usuarios externos que ya estén en el directorio)
    
    Para obtener más información, consulte [Administrar el uso compartido externo en su entorno de SharePoint Online](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85).
    
  
- En los grupos de Office 365: **Let group owners add people outside the organization to groups** (Permitir que los propietarios de grupo agreguen a los grupos personas externas a la organización)
    
    Para obtener más información, consulte [Controlar el acceso de invitado a Microsoft Teams](#controlguest).
  

La configuración de usuarios externos de SharePoint Online se puede administrar para el sitio de equipos conectados a Teams. Si desea más detalles, vea [Administrar la configuración de su sitio de grupo de SharePoint](https://support.office.com/en-us/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).﻿