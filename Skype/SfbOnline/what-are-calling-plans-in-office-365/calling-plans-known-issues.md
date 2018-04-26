---
title: Problemas conocidos de los planes de llamada
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Learn known issues with the calling plan for Office 365 (PSTN Calling) and what you can do about them. '
ms.openlocfilehash: d201db80c2da09223d8e3b1935c383089f997382
ms.sourcegitcommit: f942232d43fc4ad56b34dd400fdb4bca39013f5f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="calling-plans-known-issues"></a>Problemas conocidos de los planes de llamada

Planes de llamada Office 365 son una nueva característica que se encuentra en Skype para los negocios en línea. Los siguientes son problemas actuales que se realiza un seguimiento e investigar activamente. Se resolverán potencialmente cuando se actualiza la característica en las futuras revisiones de Office 365 y Skype para los negocios en línea.
  
## <a name="calling-plans-known-issues"></a>Problemas conocidos de los planes de llamada

|**Problema conocido**|**Comentarios**|
|:-----|:-----|
|Transición de Tech Preview licencias para las licencias de producción para llamar a los planes no actualizan automáticamente la licencia.  <br/> |En primer lugar a adquirir las licencias nuevo para que estén preparados para asignarse a los usuarios. Quitar la licencia de promoción (Tech Preview) de un usuario y asignar **inmediatamente** las nuevas licencias de **Plan de llamadas nacionales** o **nacionales y Plan de llamadas internacionales** al usuario. <br/> Si va a quitar y agregar licencias para varios usuarios, es muy importante que quite las licencias de todos los usuarios que usen Windows PowerShell y que después asigne **INMEDIATAMENTE** las licencias de todos los usuarios que usen Windows PowerShell. Haciendo esto se asegurará de que no hay ninguna interrupción del servicio cuando se manejan grandes volúmenes de asignaciones de licencias de usuario. Para secuencias de comandos de PowerShell de ejemplo, vea [Asignar Skype para licencias de negocio y equipos de Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).  <br/> **Nota:** Si utiliza conectividad de RTC local para usuarios de híbrido, *sólo* necesitará asignar una licencia de **Sistema de teléfono** . **No** debe asignar también una Plan de llamadas de voz. Sin embargo, si va a habilitar llamando a planes de Office 365 para los usuarios que se encuentran en Office 365, debe asignar sigue un **Plan de llamadas nacionales** o una licencia **nacional y Plan de llamadas internacionales** para esos usuarios. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

> [!NOTE]
> Si necesita obtener más números de teléfono que esto, ponte [en contacto con soporte técnico para productos de empresa - Admin ayuda](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |
   
## <a name="related-topics"></a>Temas relacionados
[Preguntas comunes sobre la transferencia de números de teléfono](transferring-phone-numbers-common-questions.md)

[Diferentes tipos de números de teléfono que se usan para Planes de llamada](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Administrar los números de teléfono para su organización](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Términos y condiciones de las llamadas de emergencia](../legal-and-regulatory/emergency-calling-terms-and-conditions.md)

[Skype Empresarial Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 