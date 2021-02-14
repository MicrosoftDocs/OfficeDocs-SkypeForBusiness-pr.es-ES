---
title: Configurar el enrutamiento directo
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo configurar el enrutamiento directo de Microsoft Phone System para conectar su infraestructura de telefonía local a Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5388c93e741323d3dc9eda0fc51968b8b344d2cb
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701298"
---
# <a name="configure-direct-routing"></a>Configurar el enrutamiento directo

El enrutamiento directo de Microsoft Phone System le permite conectar su infraestructura de telefonía local a Microsoft Teams. En el artículo se enumeran los pasos de alto nivel necesarios para conectar un controlador de borde de sesión (SBC) local compatible con el enrutamiento directo y cómo configurar los usuarios de Teams para que usen el enrutamiento directo para conectarse a la red telefónica conmutada (RTC). Este artículo contiene vínculos a artículos asociados para obtener más información.  

Para obtener información sobre si el enrutamiento directo es la solución adecuada para su organización, consulte [Enrutamiento directo de sistema telefónico.](direct-routing-landing-page.md) Para obtener información sobre los requisitos previos y la planificación de la implementación, vea [Planear el enrutamiento directo.](direct-routing-plan.md)

> [!Tip]
> También puede ver la siguiente sesión para obtener información sobre las ventajas del enrutamiento directo, cómo planearlo y cómo implementarlo: enrutamiento directo [en Microsoft Teams.](https://aka.ms/teams-direct-routing)

Para completar los pasos que se explican en este artículo, los administradores necesitan estar familiarizados con los cmdlets de PowerShell. Para obtener más información sobre el uso de PowerShell, vea [Configurar el equipo para Windows PowerShell.](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) 

Antes de realizar los pasos de estos artículos, Microsoft recomienda confirmar que su SBC ya se ha configurado según lo recomendado por su proveedor de SBC: 

- [Documentación de implementación de AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentación de implementación de Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentación de implementación de comunicaciones de la cinta de opciones](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentación de implementación de TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Documentación de implementación de Metacambio](https://www.metaswitch.com/products/core-network/perimeta-sbc)

Para obtener una lista completa de los SBC compatibles, vea lista de controladores de [borde de sesión certificados para enrutamiento directo.](direct-routing-border-controllers.md)

Para configurar Microsoft Phone System y permitir que los usuarios usen el enrutamiento directo, siga estos pasos: 

- **Paso 1.** [Conectar el SBC con Microsoft Phone System y validar la conexión](direct-routing-connect-the-sbc.md)
- **Paso 2.** [Habilitar a los usuarios el enrutamiento directo, la voz y el correo de voz](direct-routing-enable-users.md)
- **Paso 3.** [Configurar el enrutamiento de voz](direct-routing-voice-routing.md)
- **Paso 4.** [Traducir números a un formato alternativo](direct-routing-translate-numbers.md) 

Si va a configurar un SBC para varios inquilinos, también querrá leer Configurar un SBC para [varios inquilinos.](direct-routing-sbc-multiple-tenants.md)


## <a name="related-topics"></a>Temas relacionados

[Enrutamiento directo del Sistema telefónico](direct-routing-landing-page.md)

[Planear el enrutamiento directo](direct-routing-plan.md)

