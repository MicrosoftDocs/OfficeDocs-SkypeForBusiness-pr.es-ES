---
title: Problemas conocidos de los planes de llamada
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Calling Plans
description: "Obtenga información acerca de problemas conocidos relacionados con el plan de llamadas para Office 365 (PSTN llamando) y qué se puede hacer acerca de ellos. "
ms.openlocfilehash: 42b282bce7ba65dc4e053020970a02e71c98b5bd
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="calling-plans-known-issues"></a>Problemas conocidos de los planes de llamada

Planes de llamada Office 365 son una nueva característica que se encuentra en Skype para los negocios en línea. Los siguientes son problemas actuales que se realiza un seguimiento e investigar activamente. Se resolverán potencialmente cuando se actualiza la característica en las futuras revisiones de Office 365 y Skype para los negocios en línea.
  
## <a name="calling-plans-known-issues"></a>Problemas conocidos de los planes de llamada

|**Problema conocido**|**Comentarios**|
|:-----|:-----|
|Transición de Tech Preview licencias para las licencias de producción para llamar a los planes no actualizan automáticamente la licencia.  <br/> |En primer lugar a adquirir las licencias nuevo para que estén preparados para asignarse a los usuarios. Quitar la licencia de promoción (Tech Preview) de un usuario y asignar **inmediatamente** las nuevas licencias de **Plan de llamadas nacionales** o **nacionales y Plan de llamadas internacionales** al usuario. <br/> Si va a quitar y agregar licencias para varios usuarios, es extremadamente importante que quita las licencias de todos los usuarios con Windows PowerShell y, a continuación, asignar **inmediatamente** las licencias para todos los usuarios también mediante Windows PowerShell. Haciendo esto se asegurará de que no hay ninguna interrupción del servicio cuando se manejan grandes volúmenes de asignaciones de licencias de usuario. Para secuencias de comandos de PowerShell de ejemplo, vea [Asignar Skype para licencias de negocio y equipos de Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).  <br/> **Nota:** Si utiliza conectividad de RTC local para usuarios de híbrido, *sólo* necesitará asignar una licencia de **Sistema de teléfono** . **No** debe asignar también una Plan de llamadas de voz. Sin embargo, si va a habilitar llamando a planes de Office 365 para los usuarios que se encuentran en Office 365, debe asignar sigue un **Plan de llamadas nacionales** o una licencia **nacional y Plan de llamadas internacionales** para esos usuarios. Consulte [Asignar Skype para licencias de negocio y equipos de Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

> [!NOTE]
> Si necesita obtener más números de teléfono que esto, ponte [en contacto con soporte técnico para productos de empresa - Admin ayuda](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |
   
## <a name="related-topics"></a>Temas relacionados
[Transferencia de preguntas habituales de los números de teléfono](transferring-phone-numbers-common-questions.md)

[Diferentes tipos de números de teléfono utilizados para llamar a planes](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Administrar números de teléfono de la organización](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Términos y condiciones de las llamadas de emergencias](emergency-calling-terms-and-conditions.md)

[Skype para los negocios en línea: etiqueta de descargo de responsabilidad llamada de emergencia](https://go.microsoft.com/fwlink/?LinkID=692099)
