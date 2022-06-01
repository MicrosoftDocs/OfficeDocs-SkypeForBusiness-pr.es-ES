---
title: Teams plan de actualización de caso de caso de voz de Contoso
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
description: 'Teams caso práctico de voz para la corporación multinacional: Planificación de actualización.'
appliesto:
- Microsoft Teams
ms.openlocfilehash: 39cfd66f0ff34fb0f8792871ddfdcceebb2b9961
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2022
ms.locfileid: "65822989"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a>Caso práctico de Contoso: Teams plan de actualización

En la decisión de migrar de Skype Empresarial a Teams, Contoso quería proporcionar una experiencia de transición sencilla para los usuarios finales. En lugar de cambiar a todos los usuarios a Teams al mismo tiempo, decidieron configurar la conectividad híbrida y usar el método de capacidades superpuestas para mover usuarios a Teams. Esto permitió a los usuarios de Teams y Skype Empresarial locales compartir la presencia y comunicarse. A medida que los usuarios entraron en el piloto para Sistema telefónico, se movieron al modo Solo Teams.

Para comprender conceptos fundamentales sobre la actualización, los métodos y los modos, Contoso lee los artículos siguientes:

- [Introducción a su actualización de Microsoft Teams](upgrade-start-here.md)
- [Estrategias de actualización para administradores de TI](upgrade-to-teams-on-prem-implement.md) 
- [Guía de migración e interoperabilidad](migration-interop-guidance-for-teams-with-skype.md)
 
Contoso también asistió a la sesión de Ignite 2019 [Diseñando su ruta de Skype Empresarial a Teams](https://myignite.microsoft.com/archives/IG20-OD251). Contoso ha aprendido sobre:

- Conceptos fundamentales como la interoperabilidad, la federación y el comportamiento de actualización 

- Modos de coexistencia y administración basados en TeamsUpgradePolicy 

- Experiencia del usuario final para: 

  - Chat y llamadas 

  - Programación de reuniones 

  - Disponibilidad de la funcionalidad de colaboración en clientes de Teams 

Para planear y configurar la conectividad híbrida, el primer paso para mover su entorno local a la nube, Contoso lee Planear la [conectividad híbrida](/SkypeForBusiness/hybrid/plan-hybrid-connectivity) y [Configurar la conectividad híbrida](/SkypeForBusiness/hybrid/configure-hybrid-connectivity) para comprender cómo: 

  - Configure su servicio de entorno local para federar con Office 365. 

  - Configure su entorno local para confiar en Office 365 y habilitar el espacio de direcciones SIP compartido con Office 365 

  - Habilite el espacio de direcciones SIP compartido en su espacio empresarial de Office 365.

  - Utilizar el modo Islas durante el piloto técnico.

  - Cambie los usuarios al modo TeamsOnly una vez que el usuario esté habilitado para Sistema telefónico. El modo TeamsOnly es necesario para el plan de llamadas y el enrutamiento directo.
