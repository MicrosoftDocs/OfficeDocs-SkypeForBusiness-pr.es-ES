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
description: Obtenga información sobre los problemas conocidos con el plan de llamadas para llamadas RTC y qué puede hacer al respecto.
ms.openlocfilehash: 239a0c83a12ae7d5d7b0be2fcbf81bf8825dd85d8a0dcb7a880bc53ad8b8e477
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306113"
---
# <a name="calling-plans-known-issues"></a>Problemas conocidos de Planes de llamadas

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Los planes de llamadas son una nueva característica que se encuentra en Skype Empresarial Online. Los siguientes son los problemas actuales que se están siguiendo e investigando activamente. Se resolverán potencialmente cuando la característica se actualice en compilaciones futuras.
  
## <a name="calling-plans-known-issues"></a>Problemas conocidos de Planes de llamadas

|**Problema conocido**|**Comentarios**|
|:-----|:-----|
|La transición de licencias de Tech Preview a licencias de producción para planes de llamadas no actualiza automáticamente la licencia.  <br/> |Compre primero las nuevas licencias para que estén listas para asignarse a los usuarios. Quite la licencia de promoción (Tech Preview) de un usuario y,  a continuación, asigne inmediatamente al usuario las nuevas licencias del **Plan** de llamadas nacionales o nacionales e internacionales.  <br/> Si va a quitar y agregar licencias para varios usuarios, es muy importante que quite las licencias de todos los usuarios que usen Windows PowerShell y que después asigne **INMEDIATAMENTE** las licencias de todos los usuarios que usen Windows PowerShell. De este modo, se asegurará de que no haya interrupciones en el servicio al administrar grandes volúmenes de asignaciones de licencias de usuario. Para ver scripts de PowerShell de ejemplo, [vea Asignar Skype Empresarial y Microsoft Teams licencias.](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)  <br/> **Nota:** Si usa conectividad RTC local para usuarios híbridos, solo tiene que asignar una **Sistema telefónico** local.  NO también **debe** asignar un plan de llamadas de voz. Sin embargo, si habilita planes de llamadas en Microsoft 365 o Office 365 para los usuarios que se encuentran en Microsoft 365 o Office 365, debe asignar un **plan** de llamadas nacionales o una licencia del **Plan** de llamadas nacionales e internacionales para esos usuarios. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

> [!NOTE]
> Si necesita obtener más números de teléfono que este, póngase en contacto con el soporte técnico para productos [empresariales: Ayuda para administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |
   
## <a name="related-topics"></a>Temas relacionados
[Preguntas comunes sobre la transferencia de números de teléfono](/microsoftteams/transferring-phone-numbers-common-questions)

[Diferentes tipos de números de teléfono que se usan para Planes de llamada](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Administrar los números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[Términos y condiciones de las llamadas de emergencia](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype Empresarial Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
