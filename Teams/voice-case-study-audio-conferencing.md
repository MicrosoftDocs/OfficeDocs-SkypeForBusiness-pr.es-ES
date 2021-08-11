---
title: 'Teams caso práctico de Contoso de voz: Audioconferencia'
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 'Teams caso de voz para la corporación multinacional: Audioconferencia'
appliesto:
- Microsoft Teams
ms.openlocfilehash: f25fa2e81244365d1c0c3dfcacf918f1b35a6fa71d2b619eaaa55c8aa219c310
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54335800"
---
# <a name="contoso-case-study-audio-conferencing"></a>Caso práctico de Contoso: Audioconferencia

Para comprender lo que es la audioconferencia, lo que cuesta, la disponibilidad y cómo funciona Contoso revisó &mdash; &mdash; [Audioconferencia](deploy-audio-conferencing-teams-landing-page.md)en Office 365 . 

## <a name="overview"></a>Información general 

Para las audioconferencias, Contoso usó números de teléfono bien conocidos dentro de la organización, así como de forma externa. Como Contoso quería mantener estos números siempre que fuera posible, revisaron la información sobre cómo asignar números de teléfono dedicados y compartidos al puente de audioconferencia. 

En función de su investigación, Contoso tomó las siguientes decisiones: 

- Solo un segmento de la población que hospeda llamadas de audioconferencia periódicamente recibiría licencias de audioconferencia. 

- Contoso usaría números de teléfono dedicados y portabilidad de sus números existentes para usarlos con audioconferencias.   

Dado que los usuarios de Contoso Skype Empresarial y todos los buzones de los usuarios residen en línea, muchos usuarios tienen reuniones existentes programadas. Contoso leyó Usar el servicio de migración de reuniones [(MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json) para saber que las reuniones existentes se actualizan automáticamente para Contoso cuando cambian el usuario final al modo TeamsOnly.  


## <a name="configuration"></a>Configuración

Teléfono los números asociados a las audioconferencias se denominan números de servicio dentro de Sistema telefónico. 

- Para ubicaciones que usan planes de llamadas, para portabilidad de sus números de teléfono existentes de su operador de teléfono a Office 365, Contoso siguió los pasos de Obtener números [de teléfono de servicio.](getting-service-phone-numbers.md)

- Para asignar la licencia de Conferencias de audio al usuario final en el piloto técnico, el administrador de Contoso siguió los pasos descritos en Administrar la configuración de [audioconferencia de su organización.](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md) 

- Para el piloto empresarial y la migración, Contoso usó licencias [basadas](/azure/active-directory/users-groups-roles/licensing-groups-assign)en grupos siguiendo los pasos de Asignar licencias a los usuarios por pertenencia a grupos en Azure Active Directory .  

 

