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
f1.keywords:
- NOCSH
ms.custom:
- Calling Plans
description: Obtenga información sobre problemas conocidos con el plan de llamadas RTC y qué puede hacer al respecto.
ms.openlocfilehash: 3a97057f61c154ded83b85becbfcf53dc2b4bc78
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220740"
---
# <a name="calling-plans-known-issues"></a>Problemas conocidos de Planes de llamadas

Los planes de llamadas son una nueva característica que se encuentra en Skype Empresarial Online. Los siguientes son los problemas actuales a los que se está haciendo un seguimiento e investigando activamente. Se resolverán potencialmente cuando la característica se actualice en compilaciones futuras.
  
## <a name="calling-plans-known-issues"></a>Problemas conocidos de Planes de llamadas

|**Problema conocido**|**Comentarios**|
|:-----|:-----|
|Al cambiar de licencias de Tech Preview a licencias de producción para planes de llamadas, la licencia no se actualiza automáticamente.  <br/> |Primero compre las nuevas licencias para que estén listas para su asignación a los usuarios. Quite la licencia de promoción (Tech Preview) de un usuario y, a continuación, asigne INMEDIATAMENTE las nuevas licencias del plan de llamadas nacionales o del  **plan** de llamadas nacionales e internacionales al usuario.  <br/> Si va a quitar y agregar licencias para varios usuarios, es muy importante que quite las licencias de todos los usuarios que usen Windows PowerShell y que después asigne **INMEDIATAMENTE** las licencias de todos los usuarios que usen Windows PowerShell. De este modo, se garantiza que no haya ninguna interrupción del servicio al gestionar grandes volúmenes de asignaciones de licencias de usuario. Para ver scripts de PowerShell de ejemplo, consulte Asignar licencias de Skype Empresarial [y Microsoft Teams.](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)  <br/> **Nota:** Si usa la conectividad con RTC local para  usuarios híbridos, solo tiene que asignar una licencia **de Sistema** telefónico. NO debe **asignar** tampoco un plan de llamadas de voz. Sin embargo, si habilita planes de llamadas en Microsoft 365 u Office 365 para los usuarios que están en Microsoft 365 u Office 365, tendrá que asignar un **plan** de llamadas nacionales o un **plan** de llamadas nacionales e internacionales para esos usuarios. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

> [!NOTE]
> Si necesita obtener más números de teléfono, póngase en contacto con el servicio de soporte técnico [para productos empresariales: ayuda para administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |
   
## <a name="related-topics"></a>Temas relacionados
[Preguntas comunes sobre la transferencia de números de teléfono](/microsoftteams/transferring-phone-numbers-common-questions)

[Diferentes tipos de números de teléfono que se usan para Planes de llamada](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Administrar los números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[Términos y condiciones de las llamadas de emergencia](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype Empresarial Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
