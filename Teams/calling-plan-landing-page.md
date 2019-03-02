---
title: Planes de llamada en los equipos de Microsoft
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
description: Llamar a la página de inicio del Plan
appliesto:
- Microsoft Teams
ms.openlocfilehash: cce239825389e11cfbc627d518e7d1e459fa77d3
ms.sourcegitcommit: 59eda0c17ff39a3e6632810391d78bbadc214419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/01/2019
ms.locfileid: "30351501"
---
# <a name="phone-system-with-calling-plans"></a>Sistema telefónico con Planes de llamada 

Se ha completado la [Introducción](get-started-with-teams-quick-start.md). Ha implementado Teams con [chat, equipos, canales y aplicaciones](deploy-chat-teams-channels-microsoft-teams-landing-page.md) en toda la organización. Es posible que haya implementado [conferencia & de las reuniones](deploy-meetings-microsoft-teams-landing-page.md). Ahora está listo para agregar las cargas de trabajo de voz de la nube y ha decidido usar el sistema telefónico de Microsoft con el Plan para llamar a para conectarse a la red telefónica pública conmutada (RTC). 

En este artículo se describe la implementación las decisiones principales para llamar a los planes, así como consideraciones adicionales que es posible que desea configurar, en función de las necesidades de su organización. También debe leer [En la nube de voz en los equipos de Microsoft](cloud-voice-landing-page.md) para obtener más información acerca de las ofertas de voz de la nube de Microsoft.


## <a name="learn-more-about-calling-plans"></a>Encontrará más información acerca de los planes de llamada

Los artículos siguientes proporcionan más información sobre la implementación y uso de llamar a los planes de Microsoft:

- [Sistema telefónico de Office 365](what-is-phone-system-in-office-365.md)
- [Planes de llamadas para Office 365](calling-plans-for-office-365.md)
- [Configurar planes de llamadas](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a>Decisiones de implementación principales

Para usar Microsoft como su operador de telefonía, debe obtener licencias de llamar a planear y asignarlos a los usuarios del sistema telefónico. 

Hay dos tipos de planes de llamada disponibles:

- Planes de llamada nacionales 
- Planes de llamada nacional e internacional

|Pregúntese lo siguiente:|Acción |
|------------|-------|
|¿Son planes de llamada disponibles en Mi área? ¿Las ubicaciones de usuario tendrá planeación de llamar al servicio? | Para obtener más información, vea [disponibilidad de país y región para las conferencias de Audio y planes de llamada](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md). | 
¿Mis usuarios necesitan llamadas internacionales? | Para obtener más información, vea [Llamar a planes de Office 365](calling-plans-for-office-365.md). |
¿Mis usuarios tienen una llamada a los planes de licencias? | Para comprar y asignar licencias, vea [paso 2: comprar y asignar licencias](set-up-calling-plans.md#step-2-buy-and-assign-licenses). |
¿Mis usuarios tienen un directo hacia dentro de marcado de número de teléfono (DID)? | Para obtener los números de teléfono, vea [paso 3: obtener los números de teléfono](set-up-calling-plans.md#step-3-get-phone-numbers). |
|||

### <a name="transfer-phone-numbers-to-office-365"></a>Transferir números de teléfono a Office 365

Es fácil transferir sus números de teléfono de su proveedor de servicios actual a los equipos. Después de que el puerto sus números de teléfono a los equipos, Microsoft se convertirán en su proveedor de servicios y bill correspondiente a los números de teléfono. Para obtener más información, vea [transferir los números de teléfono para Office 365](transfer-phone-numbers-to-office-365.md).


### <a name="phone-numbers-and-emergency-locations"></a>Números de teléfono y ubicaciones de emergencia

Con una llamada a los planes en Office 365, todos los usuarios de su organización necesita tener un único marcado entrante directo (DID) número de teléfono y una dirección de emergencia validada correspondiente. También puede especificar una ubicación de emergencia dentro de la dirección de emergencia (por ejemplo, un número de oficina o número de piso). 

|Pregúntese lo siguiente:|Acción |
|:------------|:-------|
|¿El nivel de detalle quiero la información de dirección y ubicación de emergencia a ser? |Para obtener más información, vea [¿Cuáles son las ubicaciones de emergencia, las direcciones y el enrutamiento de llamadas?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).


### <a name="calling-identity"></a>Identidad de llamada

De forma predeterminada, todas las llamadas salientes utilizan el número de teléfono asignado como llamada identidad (identificador de autor de la llamada). El destinatario de la llamada puede identificar rápidamente a la persona que llama y decidir si desea aceptar o rechazar la llamada.

|Pregúntese lo siguiente:|Acción |
|:------------|:-------|
|¿Desea enmascarar o deshabilitar el identificador de autor de la llamada? | Para cambiar o bloquear el identificador de autor de la llamada, vea [establecer el identificador de autor de la llamada de un usuario](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user). |
|||




