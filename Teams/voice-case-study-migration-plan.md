---
title: Teams plan de actualización de casos prácticos de Contoso de voz
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
description: 'Teams caso de voz para empresas multinacionales: Planificación de actualizaciones.'
appliesto:
- Microsoft Teams
ms.openlocfilehash: a458f2c98b0f6de8bc2d3b3d23e2b68e4cadd931
ms.sourcegitcommit: b387296c043fcf10fba7b9ef416328383e54a565
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/26/2021
ms.locfileid: "53587449"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a>Caso práctico de Contoso: Teams plan de actualización

En la decisión de migrar de Skype Empresarial a Teams, Contoso quería proporcionar una experiencia de transición fácil para los usuarios finales. En lugar de cambiar todos a Teams al mismo tiempo, decidieron configurar la conectividad híbrida y usar el método de capacidades superpuestas para mover usuarios a Teams. Esto permitía a los usuarios Teams y Skype Empresarial local para compartir presencia y comunicarse. Cuando los usuarios entraron en el piloto Sistema telefónico, se movieron al Teams solo.

Para comprender conceptos fundamentales sobre la actualización, los métodos y los modos, Contoso leyó los siguientes artículos:

- [Introducción a su actualización de Microsoft Teams](upgrade-start-here.md)
- [Estrategias de actualización para administradores de TI](upgrade-to-teams-on-prem-implement.md) 
- [Guía de migración e interoperabilidad](migration-interop-guidance-for-teams-with-skype.md)
 
Contoso también asistió a la sesión Ignite 2019 Diseñando la ruta de acceso de Skype Empresarial [a Teams](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions). Contoso ha aprendido acerca de:

- Conceptos fundamentales como interoperabilidad, federación y comportamiento de actualización 

- Modos de coexistencia y administración basados en TeamsUpgradePolicy 

- Experiencia de usuario final para: 

  - Chat y llamadas 

  - Programación de reuniones 

  - Disponibilidad de la funcionalidad de colaboración en Teams clientes 

Para planear y configurar la conectividad híbrida, el primer paso para [](/SkypeForBusiness/hybrid/plan-hybrid-connectivity) mover su entorno local a la nube, Contoso leyó Planear conectividad híbrida y [Configurar](/SkypeForBusiness/hybrid/configure-hybrid-connectivity) conectividad híbrida para comprender cómo: 

  - Configure su servicio de entorno local para federar con Office 365. 

  - Configure su entorno local para confiar en Office 365 y habilitar el espacio de direcciones SIP compartido con Office 365 

  - Habilite el espacio de direcciones SIP compartido en Office 365 inquilino.

  - Use el modo Islas durante el piloto técnico.

  - Cambiar usuarios al modo TeamsOnly una vez que el usuario está habilitado para Sistema telefónico. TeamsOnly mode is required for Calling Plan and Direct Routing.
