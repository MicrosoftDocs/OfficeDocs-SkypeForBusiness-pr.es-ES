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
f1.keywords:
- NOCSH
ms.reviewer: crowe
search.appverid: MET150
description: Determine el plan de llamadas de sistema de Microsoft Phone que ofrecerá mejor a su organización la voz en la nube de Teams.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b1fb0abed3477039f4c19c0e2de0ea696626f35
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905032"
---
# <a name="which-calling-plan-is-right-for-you"></a>¿Qué plan de llamada es adecuado para usted? 

Has completado la [Introducción](get-started-with-teams-quick-start.md). Ha implementado Teams con [chat, equipos, canales y aplicaciones](deploy-chat-teams-channels-microsoft-teams-landing-page.md) en toda la organización. Es posible que haya implementado [reuniones & conferencias](deploy-meetings-microsoft-teams-landing-page.md). Ahora está listo para agregar cargas de trabajo de voz de nube y ha decidido usar el sistema de teléfono de Microsoft con el plan de llamadas para conectarse a la red de telefonía pública conmutada (RTC). 

En este artículo se describen las decisiones básicas de implementación para la llamada a planes, así como consideraciones adicionales que es posible que desee configurar en función de las necesidades de su organización. También debe leer [la voz de nube en Microsoft Teams](cloud-voice-landing-page.md) para obtener más información sobre las ofertas de voz de nube de Microsoft.


## <a name="learn-more-about-calling-plans"></a>Más información sobre los planes de llamadas

Los artículos siguientes proporcionan más información sobre la implementación y el uso de los planes de llamadas de Microsoft:

- [Sistema telefónico en Office 365](what-is-phone-system-in-office-365.md)
- [Planes de llamadas para Office 365](calling-plans-for-office-365.md)
- [Configurar planes de llamadas](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a>Decisiones de implementación principales

Para usar Microsoft como su operador de telefonía, debe obtener las licencias del plan de llamadas y asignarlas a los usuarios del sistema telefónico. 

Existen dos tipos de planes de llamadas:

- Planes de llamadas nacionales 
- Planes de llamadas nacionales e internacionales

|Pregúntese lo siguiente:|Acción |
|------------|-------|
|¿Están disponibles los planes de llamadas en mi área? ¿Qué ubicaciones de usuarios tendrán el servicio de plan de llamadas? | Para obtener más información, consulte [disponibilidad de países y regiones para las conferencias de audio y los planes de llamadas](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md). | 
¿Los usuarios necesitan llamadas internacionales? | Para obtener más información, consulte [planes de llamadas para Office 365](calling-plans-for-office-365.md). |
¿Tienen mis usuarios licencias de planes de llamadas? | Para comprar y asignar licencias, consulte el [paso 2: comprar y asignar licencias](set-up-calling-plans.md#step-2-buy-and-assign-licenses). |
¿Cada uno de mis usuarios tiene un número de teléfono de marcado directo? | Para obtener números de teléfono, consulte [paso 3: obtener números de teléfono](set-up-calling-plans.md#step-3-get-phone-numbers). |
|||

### <a name="transfer-phone-numbers-to-office-365"></a>Transferir números de teléfono a Office 365

Es fácil transferir los números de teléfono de su proveedor de servicios actual a teams. Después de trasladar los números de teléfono a Teams, Microsoft se convertirá en su proveedor de servicios y le facturará los números de teléfono. Para obtener más información, consulte [transferir números de teléfono a teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).


### <a name="phone-numbers-and-emergency-locations"></a>Números de teléfono y ubicaciones de emergencia

Con los planes de llamadas en Office 365, todos los usuarios de su organización necesitan tener un número de teléfono de marcado directo exclusivo y una dirección de emergencia validada correspondiente. También puedes especificar una ubicación de emergencia dentro de la dirección de emergencia (por ejemplo, un número de oficina o un número de piso). 

|Pregúntese lo siguiente:|Acción |
|:------------|:-------|
|¿Qué grado de detalle quiero que sea la dirección de emergencia y la información de ubicación? |Para obtener más información, vea [¿Qué son las ubicaciones de emergencia, las direcciones y el enrutamiento de llamadas?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)


### <a name="calling-identity"></a>Identidad de llamadas

De forma predeterminada, todas las llamadas salientes usan el número de teléfono asignado como identidad de llamada (identificación de llamada). El destinatario de la llamada puede identificar rápidamente a la persona que llama y decidir si desea aceptar o rechazar la llamada.

|Pregúntese lo siguiente:|Acción |
|:------------|:-------|
|¿Quiero enmascarar o deshabilitar la identificación de llamadas? | Para cambiar o bloquear la identificación de llamadas, vea [establecer la identificación de llamadas de un usuario](set-the-caller-id-for-a-user.md). |
|||




