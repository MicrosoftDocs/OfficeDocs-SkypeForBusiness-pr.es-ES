---
title: Configurar el enrutamiento directo
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
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
description: Obtenga información sobre cómo configurar Teléfono Microsoft System Direct Routing para conectar su infraestructura de telefonía local a Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 05e3152c13b0cf6559964d3926d7c66e7cf376e8
ms.sourcegitcommit: 197debacdcd1f7902f6e16940ef9bec8b07641af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "60634899"
---
# <a name="configure-direct-routing"></a>Configurar el enrutamiento directo

Teléfono Microsoft System Direct Routing le permite conectar su infraestructura de telefonía local a Microsoft Teams. En el artículo se enumeran los pasos de alto nivel necesarios para conectar un controlador de borde de sesión (SBC) local compatible con enrutamiento directo y cómo configurar Teams los usuarios para que usen enrutamiento directo para conectarse a la red telefónica conmutada (RTC) pública. En este artículo se vincula a artículos asociados para obtener más información.  

Para obtener información sobre si enrutamiento directo es la solución adecuada para su organización, [vea Sistema telefónico enrutamiento directo.](direct-routing-landing-page.md) Para obtener información sobre los requisitos previos y la planificación de la implementación, vea [Planear enrutamiento directo.](direct-routing-plan.md)

> [!Tip]
> También puede ver la siguiente sesión para obtener información sobre las ventajas de Enrutamiento directo, cómo planearlo y cómo implementarlo: Enrutamiento directo [en Microsoft Teams](https://aka.ms/teams-direct-routing).

Para completar los pasos explicados en este artículo, los administradores necesitan cierta familiaridad con los cmdlets de PowerShell. Para obtener más información sobre el uso de PowerShell, vea [Configurar el equipo para Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 

Antes de realizar los pasos de estos artículos, Microsoft recomienda que confirme que su SBC ya se ha configurado según lo recomendado por su proveedor de SBC: 

- [Documentación de implementación de AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentación de implementación de Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentación de implementación de Comunicaciones de la cinta de opciones](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentación de implementación de TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Documentación de implementación de Metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)

Para obtener una lista completa de SBC compatibles, vea Lista de controladores de [borde de sesión certificados para enrutamiento directo.](direct-routing-border-controllers.md)

Para configurar Teléfono Microsoft sistema y permitir a los usuarios usar enrutamiento directo, siga estos pasos: 

- **Paso 1.** [Conectar el SBC con Teléfono Microsoft y validar la conexión](direct-routing-connect-the-sbc.md)
- **Paso 2.** [Habilitar usuarios para enrutamiento directo, voz y correo de voz](direct-routing-enable-users.md)
- **Paso 3.** [Configurar el enrutamiento de llamadas](direct-routing-voice-routing.md)
- **Paso 4.** [Traducir números a un formato alternativo](direct-routing-translate-numbers.md) 

Si está configurando un SBC para varios inquilinos, también querrá leer Configurar un [SBC para varios inquilinos.](direct-routing-sbc-multiple-tenants.md)


## <a name="related-topics"></a>Temas relacionados

[Enrutamiento directo del Sistema telefónico](direct-routing-landing-page.md)

[Planear el enrutamiento directo](direct-routing-plan.md)