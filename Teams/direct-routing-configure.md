---
title: Configurar el enrutamiento directo
ms.reviewer: filippse
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
description: Obtenga información sobre cómo configurar El enrutamiento directo de Microsoft para conectar su infraestructura de telefonía local a Teams Phone System.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cf6a180b558edad23450fad3991ee2c646f6cf55
ms.sourcegitcommit: 830357674103c0c5c99bd73d40261afe02a2da49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/09/2022
ms.locfileid: "67291406"
---
# <a name="configure-direct-routing"></a>Configurar el enrutamiento directo

Enrutamiento directo le permite conectar su infraestructura de telefonía local a Microsoft Teams. En el artículo se enumeran los pasos de alto nivel necesarios para conectar un controlador de borde de sesión local (SBC) compatible con el enrutamiento directo y cómo configurar los usuarios de Teams para que usen el enrutamiento directo para conectarse a la red telefónica conmutada (RTC). Este artículo contiene vínculos a artículos asociados para obtener más información.  

Para obtener información sobre si el enrutamiento directo es la solución adecuada para su organización, vea [Opciones de conectividad con RTC](pstn-connectivity.md). Para obtener información sobre los requisitos previos y planear la implementación, vea [Planear el enrutamiento directo](direct-routing-plan.md).

Para completar los pasos que se explican en este artículo, los administradores necesitan estar familiarizados con los cmdlets de PowerShell. Para obtener más información sobre el uso de PowerShell, vea [Configurar el equipo para Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 

Antes de realizar los pasos descritos en estos artículos, Microsoft recomienda que confirme que su SBC ya se ha configurado según lo recomendado por su proveedor de SBC: 

- [Documentación de implementación de AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentación de implementación de Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentación de implementación de comunicaciones de la cinta de opciones](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentación de implementación de TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Documentación de implementación de Metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)

Para obtener una lista completa de los SBCs compatibles, consulta [Controladores de borde de sesión certificados para enrutamiento directo](direct-routing-border-controllers.md).

Para configurar el sistema telefónico y permitir que los usuarios usen el enrutamiento directo, siga estos pasos: 

- **Paso 1.** [Conectar el SBC con el sistema telefónico y validar la conexión](direct-routing-connect-the-sbc.md)
- **Paso 2.** [Habilitar a los usuarios para el enrutamiento directo, la voz y el correo de voz](direct-routing-enable-users.md)
- **Paso 3.** [Configurar el enrutamiento de llamadas](direct-routing-voice-routing.md)
- **Paso 4.** [Traducir números a un formato alternativo](direct-routing-translate-numbers.md) 

Si está configurando un SBC para varios inquilinos, también querrá leer [Configurar un SBC para varios inquilinos](direct-routing-sbc-multiple-tenants.md).

## <a name="support-boundaries"></a>Límites de soporte técnico
Microsoft solo admite un sistema telefónico con enrutamiento directo cuando se usa con dispositivos certificados. Si hay problemas, primero debe ponerse en contacto con el servicio de atención al cliente de su proveedor de SBC. Si es necesario, el proveedor de CLS remitirá el problema a Microsoft a través de canales internos. Microsoft se reserva el derecho a rechazar casos de soporte técnico de dispositivos no certificados conectados al Sistema telefónico a través del Enrutamiento directo. Si Microsoft determina que el problema de Enrutamiento directo de un cliente está relacionado con el dispositivo de un proveedor de CLS, el cliente deberá ponerse en contacto con el proveedor de CLS para obtener soporte técnico.

## <a name="related-topics"></a>Temas relacionados

[Planear la solución de voz](cloud-voice-landing-page.md)

[Opciones de conectividad con RTC](pstn-connectivity.md)

[Planear el enrutamiento directo](direct-routing-plan.md)
