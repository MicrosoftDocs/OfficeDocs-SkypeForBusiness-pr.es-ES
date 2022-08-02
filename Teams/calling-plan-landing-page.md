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
description: Determine qué plan de llamadas de Microsoft Phone System servirá mejor a su organización en Cloud Voice en Teams.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0040814b12e98c4f44d1dff5939651938580fa4d
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2022
ms.locfileid: "67156558"
---
# <a name="which-calling-plan-is-right-for-you"></a>¿Qué plan de llamada es adecuado para usted?

Ya ha completado la [Introducción](get-started-with-teams-quick-start.md). Ha implementado Teams con [chat, equipos, canales y aplicaciones](deploy-chat-teams-channels-microsoft-teams-landing-page.md) en toda la organización. Es posible que haya implementado [Reuniones & conferencias](deploy-meetings-microsoft-teams-landing-page.md). Ahora ya está listo para agregar cargas de trabajo de voz en la nube y ha decidido usar Microsoft Phone System con Plan de llamadas para conectarse a la red telefónica conmutada (RTC).

En este artículo se describen las decisiones básicas de implementación para planes de llamadas y otras consideraciones que puede que desee configurar, en función de las necesidades de su organización. También debería leer [Cloud Voice en Microsoft Teams](cloud-voice-landing-page.md) para obtener más información sobre las ofertas de voz en la nube de Microsoft.

## <a name="learn-more-about-calling-plans"></a>Más información sobre planes de llamadas

En los artículos siguientes se proporciona más información sobre cómo implementar y usar planes de llamadas de Microsoft:

- [Sistema telefónico en Microsoft 365 o Office 365](what-is-phone-system-in-office-365.md)
- [Planes de llamadas para Microsoft 365 o Office 365](calling-plans-for-office-365.md)
- [Configurar planes de llamadas](set-up-calling-plans.md)

## <a name="core-deployment-decisions"></a>Decisiones de implementación principales

Para usar Microsoft como su operador de telefonía, debe obtener licencias de plan de llamadas y asignarlas a los usuarios del sistema telefónico.

Hay tres tipos de planes de llamada disponibles:

- Planes de llamadas nacionales
- Planes de llamadas internacionales
- Planes de llamadas de pago por pago

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
| ¿Están disponibles los planes de llamadas en mi área? ¿Qué ubicaciones de usuario tendrán el servicio Plan de llamadas? | Para obtener más información, consulte [Disponibilidad de país y región para planes de llamadas y audioconferencias](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md). |
| ¿Mis usuarios necesitan llamadas internacionales? | Para obtener más información, consulte [Planes de llamadas para Microsoft 365 o Office 365](calling-plans-for-office-365.md). |
| Si algunos de mis usuarios no realizan un número significativo de llamadas salientes, ¿es el plan de llamadas de pago por uso la opción más económica para ellos? | Para obtener más información, consulte [Planes de llamadas para Microsoft 365 o Office 365](calling-plans-for-office-365.md). |
| ¿Mis usuarios tienen licencias de planes de llamadas? | Para comprar y asignar licencias, consulte [Paso 2: Comprar y asignar licencias](set-up-calling-plans.md#step-2-buy-and-assign-licenses). |
| ¿Cada uno de mis usuarios tiene un número de teléfono de marcado entrante directo (DID)? | Para obtener números de teléfono, consulte [Paso 3: Obtener números de teléfono](set-up-calling-plans.md#step-3-get-phone-numbers). |

### <a name="transfer-phone-numbers-to-microsoft-365-or-office-365"></a>Transferir números de teléfono a Microsoft 365 o Office 365

Es fácil transferir los números de teléfono de su proveedor de servicios actual a Teams. Después de transferir sus números de teléfono a Teams, Microsoft se convertirá en su proveedor de servicios y le facturará por esos números de teléfono. Para obtener más información, consulte [Transferir números de teléfono a Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).

### <a name="phone-numbers-and-emergency-locations"></a>Números de teléfono y ubicaciones de emergencia

Con planes de llamadas en Microsoft 365 o Office 365, todos los usuarios de su organización deben tener un número de teléfono único de marcado directo entrante (DID) y una dirección de emergencia validada correspondiente. También puede especificar una ubicación de emergencia dentro de la dirección de emergencia (por ejemplo, un número de oficina o un número de piso).

|Pregúntese lo siguiente:|Acción |
|:------------|:-------|
|¿Qué detalles quiero que tenga la dirección de emergencia y la información de ubicación? |Para obtener más información, vea [¿Qué son las ubicaciones de emergencia, las direcciones y el enrutamiento de llamadas?](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).

### <a name="calling-identity"></a>Identidad de llamada

De forma predeterminada, todas las llamadas salientes usan el número de teléfono asignado como identidad de llamada (identificador de llamada). El destinatario de la llamada puede identificar rápidamente a la persona que llama y decidir si desea aceptar o rechazar la llamada.

|Pregúntese lo siguiente:|Acción |
|:------------|:-------|
|¿Quiero enmascarar o deshabilitar el identificador de llamadas? | Para cambiar o bloquear el identificador de llamada, vea [Establecer el identificador de llamada de un usuario](set-the-caller-id-for-a-user.md). |
|||
