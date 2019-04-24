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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Learn known issues with the calling plan for Office 365 (PSTN Calling) and what you can do about them. '
ms.openlocfilehash: 01a49749f472b6a3e591295cff7184dc26fd564a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233229"
---
# <a name="calling-plans-known-issues"></a>Problemas conocidos de Planes de llamadas

Planes de llamada en Office 365 son una característica nueva que se encuentran en Skype para profesionales en línea. Los siguientes son problemas actuales que se va a realizar un seguimiento y activamente investigarse. Se resolverán potencialmente cuando la característica se ha actualizado en futuras versiones de Office 365 y Skype para profesionales en línea.
  
## <a name="calling-plans-known-issues"></a>Problemas conocidos de Planes de llamadas

|**Problema conocido**|**Comentarios**|
|:-----|:-----|
|Transición de Tech Preview licencias para las licencias de producción para llamar a los planes no actualizan automáticamente la licencia.  <br/> |En primer lugar a adquirir las licencias nuevo para que estén preparados ser asignado a los usuarios. Quitar la licencia de promoción (Tech Preview) de un usuario y, a continuación, asignar **inmediatamente** las licencias de **Llamar a planear nacional** o **nacionales y llamar a planear internacional de** nuevo al usuario. <br/> Si va a quitar y agregar licencias para varios usuarios, es muy importante que quite las licencias de todos los usuarios que usen Windows PowerShell y que después asigne **INMEDIATAMENTE** las licencias de todos los usuarios que usen Windows PowerShell. De esta forma se asegurará de que no hay ninguna interrupción del servicio al manejar grandes volúmenes de las asignaciones de licencia de usuario. Para los scripts de PowerShell de ejemplo, vea [Asignar Skype para licencias de negocio y equipos de Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).  <br/> **Nota:** Si está utilizando la conectividad de RTC local para los usuarios de híbrida, *sólo* tiene que asignar una licencia de **Sistema telefónico** . **No** debe asignar también una planeación de la llamada de voz. Sin embargo, si va a habilitar una llamada a los planes en Office 365 para los usuarios que se encuentran en Office 365, debe asignar aún un **Nacionales llamar a planear** o una licencia **nacionales y llamar a planear internacional** para esos usuarios. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

> [!NOTE]
> Si necesita obtener más números de teléfono que este, por favor, [póngase en contacto con soporte técnico para productos de negocio: Ayuda de administración](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |
   
## <a name="related-topics"></a>Temas relacionados
[Preguntas comunes sobre la transferencia de números de teléfono](/microsoftteams/transferring-phone-numbers-common-questions)

[Diferentes tipos de números de teléfono que se usan para Planes de llamada](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Administrar los números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[Términos y condiciones de las llamadas de emergencia](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype Empresarial Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 