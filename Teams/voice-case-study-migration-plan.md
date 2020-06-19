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
ms.openlocfilehash: d5429b4c45ccea82d1451210438bedd328618604
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786089"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a>Caso práctico de Contoso: Plan de actualización de Teams

En la decisión de migrar de Skype empresarial a Teams, contoso quería proporcionar una experiencia de transición sencilla para los usuarios finales. En lugar de cambiar a todos los equipos al mismo tiempo, decidieron configurar la conectividad híbrida y usar el método de funciones superpuestas para mover usuarios a teams. Esto permitía a los usuarios de Teams y de Skype empresarial locales compartir presencia y comunicarte. A medida que los usuarios escribieron el piloto para el sistema telefónico, se movieron al modo solo para equipos.

Para comprender los conceptos fundamentales sobre la actualización, los métodos y los modos, contoso Lee los artículos siguientes:

- [Introducción a su actualización de Microsoft Teams](upgrade-start-here.md)
- [Actualización de Skype Empresarial a Teams](upgrade-to-teams-on-prem-overview.md) 
- [Guía de migración e interoperabilidad](migration-interop-guidance-for-teams-with-skype.md)
 
Contoso también asistió a la sesión de encendido 2019, en la [que se diseña la ruta de Skype empresarial a teams](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions). Contoso aprendió acerca de:

- Conceptos fundamentales como la interoperabilidad, la Federación y el comportamiento de actualización 

- Modos de coexistencia y administración basada en TeamsUpgradePolicy 

- Experiencia de usuario final para: 

  - Conversaciones y llamadas 

  - Programación de reuniones 

  - Disponibilidad de las funciones de colaboración en los clientes de Teams 

Para planear y configurar la conectividad híbrida, el primer paso para mover su entorno local a la nube, el [plan](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) de lectura de [contoso y la conectividad híbrida](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) para comprender cómo: 

  - Configure su servicio de entorno local para federarse con Office 365. 

  - Configurar su entorno local para confiar en Office 365 y habilitar el espacio de direcciones SIP compartido con Office 365 

  - Habilite el espacio de direcciones SIP compartido en su inquilino de Office 365.

  - Use el modo islas durante el programa piloto.

  - Cambiar usuarios al modo TeamsOnly una vez que el usuario esté habilitado para el sistema telefónico. El modo TeamsOnly es necesario para llamar a plan y enrutamiento directo. 
