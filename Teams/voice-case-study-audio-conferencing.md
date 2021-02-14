---
title: Caso práctico de Teams voice Contoso
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
description: Caso práctico de voz de Teams para una corporación multinacional
appliesto:
- Microsoft Teams
ms.openlocfilehash: f58f3518202fd836ff962374e8f3b3a00ab71817
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786113"
---
# <a name="contoso-case-study-audio-conferencing"></a>Caso práctico Contoso: Audioconferencia

Para comprender qué es la audioconferencia, qué cuesta, disponibilidad y cómo funciona Contoso revisó &mdash; &mdash; Audioconferencia en Office [365.](deploy-audio-conferencing-teams-landing-page.md) 

## <a name="overview"></a>Información general 

Para las audioconferencias, Contoso usó números de teléfono conocidos dentro de la organización, así como externamente. Como Contoso quería mantener estos números siempre que fuera posible, revisaba la información sobre cómo asignar números de teléfono dedicados y compartidos al puente de audioconferencia. 

Basándose en su investigación, Contoso tomó las siguientes decisiones: 

- Solo un segmento del número de usuarios que hospedan llamadas de audioconferencia de forma periódica recibirán licencias de Audioconferencia. 

- Contoso usaría números de teléfono dedicados y portabilidad de sus números existentes para usarlos con Audioconferencia.   

Como los usuarios de Contoso usaban Skype Empresarial y todos los buzones de los usuarios residen en línea, muchos usuarios tienen reuniones existentes programadas. Contoso leyó Usar el servicio de migración de reuniones [(MMS)](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) para saber que las reuniones existentes se actualizan automáticamente para Contoso cuando cambian el usuario final al modo TeamsOnly.  


## <a name="configuration"></a>Configuración

Los números de teléfono asociados a las audioconferencias se conocen como números de servicio en Sistema telefónico. 

- Para ubicaciones con planes de llamadas, para portabilidad de sus números de teléfono existentes de su operador de telefonía a Office 365, Contoso ha seguido los pasos indicados en Obtener números [de teléfono de servicio.](getting-service-phone-numbers.md)

- Para asignar la licencia de Audioconferencia al usuario final en el piloto técnico, el administrador de Contoso siguió los pasos de Administrar la configuración de [Audioconferencia para su organización.](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md) 

- Para la migración y el piloto empresarial, Contoso usó licencias basadas en grupos siguiendo los pasos de Asignar licencias a usuarios por pertenencia a grupos [en Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)  

 

 