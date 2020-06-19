---
title: Caso práctico de voz de Contoso
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
description: Estudio de casos de voz de Teams para la corporación multinacional
appliesto:
- Microsoft Teams
ms.openlocfilehash: f58f3518202fd836ff962374e8f3b3a00ab71817
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786113"
---
# <a name="contoso-case-study-audio-conferencing"></a>Caso práctico de Contoso: audioconferencia

Para comprender las conferencias de audio &mdash; Qué es, lo que cuesta, la disponibilidad y cómo funciona la &mdash; [Conferencia de audio revisada de Contoso en Office 365](deploy-audio-conferencing-teams-landing-page.md). 

## <a name="overview"></a>Información general 

En el caso de las conferencias de audio, contoso usó números de teléfono que son bien conocidos dentro de la organización y externamente. Debido a que contoso deseaba mantener estos números siempre que sea posible, revisaron la información sobre la asignación de números de teléfono dedicados y compartidos al puente de audioconferencia. 

En función de su investigación, contoso ha tomado las siguientes decisiones: 

- Solo un segmento de la población que normalmente aloja las llamadas de las conferencias de audio recibiría licencias de audioconferencia. 

- Contoso usaría números de teléfono dedicados y trasladará los números existentes para usar con las conferencias de audio.   

Como los usuarios de Contoso usaban Skype empresarial y todos los buzones de los usuarios se encuentran en línea, muchos usuarios tienen programada una reunión. Contoso lea [con el servicio de migración de reuniones (MMS)](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) para saber que las reuniones existentes se actualizan automáticamente en Contoso cuando cambian el usuario final al modo TeamsOnly.  


## <a name="configuration"></a>Configuración

Los números de teléfono asociados a las conferencias de audio se conocen como números de servicio en el sistema telefónico. 

- Para las ubicaciones que usan planes de llamadas, para trasladar sus números de teléfono existentes desde su operador telefónico a Office 365, contoso siguió los pasos de [obtener números de teléfono de servicio](getting-service-phone-numbers.md).

- Para asignar la licencia de audioconferencia al usuario final en el piloto técnico, el administrador de Contoso siguió los pasos de [administrar la configuración de la audioconferencia para su organización](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md). 

- Para el piloto y la migración de empresas, contoso usó las licencias basadas en grupos siguiendo los pasos de [asignar licencias a usuarios por pertenencia a grupos en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).  

 

 