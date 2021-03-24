---
title: Caso práctico de Contoso de voz de Teams
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
ms.openlocfilehash: b0da56bc0da083654a0cd694bd5983f2fe4fe515
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093730"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a>Caso práctico de Contoso: Plan de actualización de Teams

En la decisión de migrar de Skype Empresarial a Teams, Contoso quería proporcionar una experiencia de transición fácil para los usuarios finales. En lugar de cambiar todos a Teams al mismo tiempo, decidieron configurar la conectividad híbrida y usar el método de capacidades superpuestas para mover usuarios a Teams. Esto permitía a los usuarios de Teams y Skype Empresarial local compartir presencia y comunicarse. Cuando los usuarios entraron en el piloto de Sistema telefónico, se movieron al modo Solo para equipos.

Para comprender conceptos fundamentales sobre la actualización, los métodos y los modos, Contoso leyó los siguientes artículos:

- [Introducción a su actualización de Microsoft Teams](upgrade-start-here.md)
- [Estrategias de actualización para administradores de TI](upgrade-to-teams-on-prem-implement.md) 
- [Guía de migración e interoperabilidad](migration-interop-guidance-for-teams-with-skype.md)
 
Contoso también asistió a la sesión Ignite 2019 Diseñando su ruta de [Skype Empresarial a Teams.](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions) Contoso ha aprendido acerca de:

- Conceptos fundamentales como interoperabilidad, federación y comportamiento de actualización 

- Modos de coexistencia y administración basados en TeamsUpgradePolicy 

- Experiencia de usuario final para: 

  - Chat y llamadas 

  - Programación de reuniones 

  - Disponibilidad de la funcionalidad de colaboración en clientes de Teams 

Para planear y configurar la conectividad híbrida, el primer paso para [](/SkypeForBusiness/hybrid/plan-hybrid-connectivity) mover su entorno local a la nube, Contoso leyó Planear conectividad híbrida y [Configurar](/SkypeForBusiness/hybrid/configure-hybrid-connectivity) conectividad híbrida para comprender cómo: 

  - Configure su servicio de entorno local para federar con Office 365. 

  - Configurar su entorno local para confiar en Office 365 y habilitar el espacio de direcciones SIP compartido con Office 365 

  - Habilitar el espacio de direcciones SIP compartido en su espacio empresarial de Office 365.

  - Use el modo Islas durante el piloto técnico.

  - Cambiar usuarios al modo TeamsOnly una vez que el usuario esté habilitado para Sistema telefónico. TeamsOnly mode is required for Calling Plan and Direct Routing.