---
title: Planes de llamadas en Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
f1.keywords:
- NOCSH
ms.reviewer: crowe
search.appverid: MET150
description: Determine qué plan de llamadas de sistema telefónico de Microsoft servirá mejor a su organización en Cloud Voice en Teams.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 71fe92646a3a2976e9a4d393e54ea56a7669b400
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031856"
---
# <a name="which-calling-plan-is-right-for-you"></a>¿Qué plan de llamada es adecuado para usted? 

Ha completado la [introducción.](get-started-with-teams-quick-start.md) Ha implementado Teams con [chat, equipos, canales y aplicaciones](deploy-chat-teams-channels-microsoft-teams-landing-page.md) en toda la organización. Es posible que haya implementado [Reuniones & conferencia.](deploy-meetings-microsoft-teams-landing-page.md) Ahora ya está listo para agregar cargas de trabajo de voz en la nube y ha decidido usar Microsoft Phone System con plan de llamadas para conectarse a la red telefónica conmutada (RTC). 

En este artículo se describen las decisiones de implementación básicas para planes de llamadas, así como consideraciones adicionales que puede que quiera configurar según las necesidades de su organización. También debe leer [Cloud Voice en Microsoft Teams](cloud-voice-landing-page.md) para obtener más información sobre las ofertas de voz en la nube de Microsoft.


## <a name="learn-more-about-calling-plans"></a>Más información sobre planes de llamadas

En los artículos siguientes se proporciona más información sobre la implementación y el uso de planes de llamadas de Microsoft:

- [Sistema telefónico en Microsoft 365 u Office 365](what-is-phone-system-in-office-365.md)
- [Planes de llamadas para Microsoft 365 u Office 365](calling-plans-for-office-365.md)
- [Configurar planes de llamadas](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a>Decisiones de implementación principales

Para usar Microsoft como su operador de telefonía, debe obtener licencias del plan de llamadas y asignarlas a los usuarios de su sistema telefónico. 

Hay dos tipos de planes de llamadas disponibles:

- Planes de llamadas nacionales 
- Planes de llamadas nacionales e internacionales

|Pregúntese lo siguiente:|Acción |
|------------|-------|
|¿Los planes de llamadas están disponibles en mi área? ¿Qué ubicaciones de usuario tendrán servicio Plan de llamadas? | Para obtener más información, consulte Disponibilidad del país y la región para planes de [audioconferencia y llamadas.](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) | 
¿Mis usuarios necesitan llamadas internacionales? | Para obtener más información, [consulte Planes de llamadas para Microsoft 365 u Office 365.](calling-plans-for-office-365.md) |
¿Tienen mis usuarios licencias de planes de llamadas? | Para comprar y asignar licencias, vea [el paso 2: Comprar y asignar licencias.](set-up-calling-plans.md#step-2-buy-and-assign-licenses) |
¿Tienen mis usuarios un número de teléfono de marcado directo (DID)? | Para obtener números de teléfono, vea [el paso 3: Obtener números de teléfono.](set-up-calling-plans.md#step-3-get-phone-numbers) |
|||

### <a name="transfer-phone-numbers-to-microsoft-365-or-office-365"></a>Transferir números de teléfono a Microsoft 365 u Office 365

Es fácil transferir sus números de teléfono desde su proveedor de servicios actual a Teams. Después de realizar la portabilidad de sus números de teléfono a Teams, Microsoft se convertirá en su proveedor de servicios y le facturará por esos números de teléfono. Para obtener más información, consulte [Transferir números de teléfono a Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)


### <a name="phone-numbers-and-emergency-locations"></a>Números de teléfono y ubicaciones de emergencia

Con los planes de llamadas en Microsoft 365 u Office 365, cada usuario de su organización debe tener un número de teléfono de marcado directo (DID) único y una dirección de emergencia validada correspondiente. También puede especificar una ubicación de emergencia dentro de la dirección de emergencia (por ejemplo, un número de oficina o un número de planta). 

|Pregúntese lo siguiente:|Acción |
|:------------|:-------|
|¿En qué medida quiero que esté la dirección de emergencia y la información de ubicación? |Para obtener más información, vea [¿Qué son las ubicaciones de emergencia, las direcciones y el enrutamiento de llamadas?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)


### <a name="calling-identity"></a>Identidad de llamada

De forma predeterminada, todas las llamadas salientes usan el número de teléfono asignado como identidad de llamada (identificador de llamada). El destinatario de la llamada puede identificar rápidamente a la persona que llama y decidir si desea aceptar o rechazar la llamada.

|Pregúntese lo siguiente:|Acción |
|:------------|:-------|
|¿Quiero enmascarar o deshabilitar la identificación de llamadas? | Para cambiar o bloquear el identificador de llamada, vea [Establecer el identificador de llamada de un usuario.](set-the-caller-id-for-a-user.md) |
|||




