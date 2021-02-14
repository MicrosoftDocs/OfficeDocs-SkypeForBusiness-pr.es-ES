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
ms.openlocfilehash: d5429b4c45ccea82d1451210438bedd328618604
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786089"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a>Caso práctico Contoso: Plan de actualización de Teams

En la decisión de migrar de Skype Empresarial a Teams, Contoso quería proporcionar una experiencia de transición sencilla para los usuarios finales. Instead of switching everyone to Teams at the same time, they decided to set up hybrid connectivity, and use the overlapping capabilities method to move users to Teams. Esto permitía a los usuarios de Teams y Skype Empresarial local compartir la presencia y comunicarse. Cuando los usuarios entraban en el programa piloto de Sistema telefónico, solo se movían al modo Teams.

Para comprender conceptos fundamentales sobre la actualización, los métodos y los modos, Contoso lea los siguientes artículos:

- [Introducción a su actualización de Microsoft Teams](upgrade-start-here.md)
- [Actualización de Skype Empresarial a Microsoft Teams](upgrade-to-teams-on-prem-overview.md) 
- [Guía de migración e interoperabilidad](migration-interop-guidance-for-teams-with-skype.md)
 
Contoso también ha participado en la sesión Ignite 2019 diseñando la ruta de [Skype Empresarial a Teams.](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions) Contoso ha aprendido acerca de:

- Conceptos fundamentales como la interoperabilidad, la federación y el comportamiento de actualización 

- Modos de coexistencia y administración basados en TeamsUpgradePolicy 

- Experiencia del usuario final para: 

  - Chat y llamadas 

  - Programación de reuniones 

  - Disponibilidad de la funcionalidad de colaboración en clientes de Teams 

Para planear y configurar la conectividad híbrida, el primer paso para mover su [](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) entorno local a la nube, Contoso lea la conectividad híbrida de [Plan](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) y Configurar conectividad híbrida para comprender cómo: 

  - Configure su servicio de entorno local para federar con Office 365. 

  - Configurar su entorno local para confiar en Office 365 y habilitar el espacio de direcciones SIP compartido con Office 365 

  - Habilite el espacio de direcciones SIP compartido en su espacio empresarial de Office 365.

  - Use el modo Islas durante el piloto técnico.

  - Cambie a los usuarios al modo TeamsOnly una vez que el usuario esté habilitado para Sistema telefónico. TeamsOnly mode is required for Calling Plan and Direct Routing. 
