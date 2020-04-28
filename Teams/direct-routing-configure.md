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
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Aprenda a configurar el enrutamiento directo de Microsoft Phone System para conectar su infraestructura de telefonía local con Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f12eb67fd63a3d1bbed3ddcd0c4fadce16529083
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904832"
---
# <a name="configure-direct-routing"></a>Configurar el enrutamiento directo

El enrutamiento directo de Microsoft Phone System le permite conectar su infraestructura de telefonía local con Microsoft Teams. En el artículo se enumeran los pasos de alto nivel necesarios para conectar un controlador de borde de sesión local compatible (SBC) con el enrutamiento directo y cómo configurar los usuarios de Teamtes para que usen el enrutamiento directo para conectarse a la red de telefonía pública conmutada (RTC). Este artículo contiene vínculos a artículos asociados para obtener más información.  

Para obtener información sobre si el enrutamiento directo es la solución adecuada para su organización, consulte [enrutamiento directo de sistema telefónico](direct-routing-landing-page.md). Para obtener información sobre los requisitos previos y la planificación de la implementación, consulte [planear el enrutamiento directo](direct-routing-plan.md).

> [!Tip]
> También puede ver la siguiente sesión para obtener información sobre las ventajas del enrutamiento directo, cómo planearla y cómo implementarla: el [enrutamiento directo en Microsoft Teams](https://aka.ms/teams-direct-routing).

Para completar los pasos que se explican en este artículo, los administradores deben estar familiarizados con los cmdlets de PowerShell. Para obtener más información sobre cómo usar PowerShell, consulte [configurar el equipo para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 

Antes de realizar los pasos de estos artículos, Microsoft le recomienda que confirme que su SBC ya se ha configurado de la manera recomendada por su proveedor de SBC: 

- [Documentación de la implementación de AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentación de implementación de Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentación de implementación de comunicaciones de la cinta](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentación de la implementación de TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Documentación de implementación de MetaSwitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)

Para obtener una lista completa de SBCs admitidos, vea [lista de controladores de borde de sesión certificados para enrutamiento directo](direct-routing-border-controllers.md).

Para configurar Microsoft Phone System y permitir que los usuarios usen el enrutamiento directo, siga estos pasos: 

- **Paso 1.** [Conectar el SBC con Microsoft Phone System y validar la conexión](direct-routing-connect-the-sbc.md)
- **Paso 2.** [Habilitar a los usuarios para el enrutamiento directo, la voz y el buzón de voz](direct-routing-enable-users.md)
- **Paso 3.** [Configurar el enrutamiento de voz](direct-routing-voice-routing.md)
- **Paso 4.** [Traducir números a un formato alternativo](direct-routing-translate-numbers.md) 

Si está configurando un SBC para varios inquilinos, también deberá leer [configurar un SBC para varios inquilinos](direct-routing-sbc-multiple-tenants.md).


## <a name="related-topics"></a>Temas relacionados

[Enrutamiento directo del Sistema telefónico](direct-routing-landing-page.md)

[Planear el enrutamiento directo](direct-routing-plan.md)

