---
title: Problemas conocidos de Planes de llamadas
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Learn known issues with the calling plan for Office 365 (PSTN Calling) and what you can do about them. '
ms.openlocfilehash: 9a6f97a93aa6c7b4e847ba1cb3280a21c473db0c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299528"
---
# <a name="calling-plans-known-issues"></a>Problemas conocidos de Planes de llamadas

Los planes de llamadas en Office 365 son una nueva característica que se encuentra en Skype empresarial online. A continuación se indican los problemas actuales de los que se realiza un seguimiento y se investigan activamente. Se resolverán potencialmente cuando la característica se actualice en las compilaciones futuras de Office 365 y Skype empresarial online.
  
## <a name="calling-plans-known-issues"></a>Problemas conocidos de Planes de llamadas

|**Problema conocido**|**Comentarios**|
|:-----|:-----|
|La transición desde las licencias Technical Preview a las licencias de producción para planes de llamadas no actualiza automáticamente la licencia.  <br/> |Compre primero sus licencias nuevas para que estén listas para su asignación a los usuarios. Elimine la licencia de la promoción (Technical Preview) de un usuario y, a continuación, asigne **inmediatamente** el nuevo **plan de llamadas nacionales** y las licencias del **plan de llamadas nacionales e internacionales** al usuario. <br/> Si va a quitar y agregar licencias para varios usuarios, es muy importante que quite las licencias de todos los usuarios que usen Windows PowerShell y que después asigne **INMEDIATAMENTE** las licencias de todos los usuarios que usen Windows PowerShell. De esta manera, se asegurará de que no se interrumpa el servicio al manejar grandes volúmenes de asignaciones de licencias de usuario. Para obtener ejemplos de scripts de PowerShell, consulte [asignar licencias de Skype empresarial y Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).  <br/> **Nota:** Si está usando la conectividad RTC local para usuarios híbridos, *solo* tiene que asignar una licencia de **sistema telefónico** . Además, **no** deberías asignar un plan de llamadas de voz. Sin embargo, si habilita planes de llamadas en Office 365 para usuarios que están en Office 365, debe asignar un **plan de llamadas nacionales** o una licencia de **plan de llamadas nacionales e internacionales** para esos usuarios. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

> [!NOTE]
> Si necesita obtener más números de teléfono, [póngase en contacto con el soporte técnico para productos para empresas: ayuda para administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |
   
## <a name="related-topics"></a>Temas relacionados
[Preguntas comunes sobre la transferencia de números de teléfono](/microsoftteams/transferring-phone-numbers-common-questions)

[Diferentes tipos de números de teléfono que se usan para Planes de llamada](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Administrar los números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[Términos y condiciones de las llamadas de emergencia](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype Empresarial Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 