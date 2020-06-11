---
title: Voz en la nube de Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- M365-voice
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
search.appverid: MET150
description: Obtenga más información sobre la característica de voz en la nube y comprenda las decisiones de implementación necesarias a las que se enfrentará.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 96d4f6b5e75e0f0f716b4f1b840b079996344cfb
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2020
ms.locfileid: "44690796"
---
# <a name="cloud-voice-in-microsoft-teams"></a>Voz en la nube de Microsoft Teams

Ha completado la [Introducción](get-started-with-teams-quick-start.md). Ha implementado Teams con [chat, equipos, canales y aplicaciones](deploy-chat-teams-channels-microsoft-teams-landing-page.md) en toda la organización. Es posible que haya implementado [reuniones & conferencias](deploy-meetings-microsoft-teams-landing-page.md). Ahora está listo para agregar funcionalidades de voz en la nube para sus usuarios. 

La voz de nube proporciona capacidades de central de conmutación (PBX) y opciones para conectarse a la red de telefonía pública conmutada (RTC).

Este artículo le ayudará a decidir si necesita cambiar cualquiera de la configuración de voz de nube predeterminada, en función del perfil y los requisitos empresariales de su organización, y luego le guiará por los cambios. La configuración se dividirá en dos grupos, empezando por el conjunto básico de [cambios que es más probable que se realicen](#core-deployment-decisions). El segundo grupo incluye las [opciones adicionales](#additional-deployment-decisions) que puede que quiera configurar, según las necesidades de su organización.

Recomendamos que todas las organizaciones prosigan las decisiones básicas y, a continuación, si su organización tiene requisitos adicionales, revise el siguiente material.



## <a name="learn-more-about-cloud-voice"></a>Más información sobre la voz de nube

Los artículos siguientes proporcionan más información sobre cómo implementar y usar las características de voz en la nube en Teams:

- [Sistema telefónico en Microsoft 365 u Office 365](what-is-phone-system-in-office-365.md)
- [Sistema telefónico con Planes de llamada](calling-plan-landing-page.md)
- [Enrutamiento directo del Sistema telefónico](direct-routing-landing-page.md)
- [Implementación de voz en la nube](cloud-voice-deployment.md)
- [Soluciones de telefonía de Microsoft](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)
- Vea la siguiente sesión para obtener más información sobre el sistema telefónico: [Introducción al sistema telefónico en Microsoft Teams](https://aka.ms/teams-phone-system)


## <a name="core-deployment-decisions"></a>Decisiones de implementación principales

Estas son las opciones que la mayoría de organizaciones cambia (si la configuración predeterminada de Teams no sirve para la organización).

## <a name="phone-system-office-365"></a>Sistema telefónico (Office 365)

Sistema telefónico es la tecnología de Microsoft para habilitar el control de llamadas y las capacidades de la central de conmutación (PBX) en la nube de Microsoft 365 o de Office 365. El sistema telefónico le permite reemplazar el sistema de central de conmutación (PBX) existente por un conjunto de características que se proporcionan directamente desde Microsoft 365 u Office 365 y están estrechamente integradas en la experiencia de productividad de nube de la empresa.


|Pregúntese lo siguiente:|Acción |
|:------------|:-------|
|¿En qué ubicaciones de usuario o oficinas implementaré el sistema telefónico? |Para obtener más información sobre el sistema telefónico, consulte [Qué es el sistema telefónico en Microsoft 365 u Office 365](what-is-phone-system-in-office-365.md).</li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a>Conexión a la red de telefonía pública conmutada (RTC)

Para conectar el sistema telefónico a la red de telefonía pública conmutada (RTC) para que los usuarios puedan hacer llamadas telefónicas en todo el mundo, tienes opciones basadas en las necesidades de tu empresa.  Pregúntese lo siguiente:


|Pregúntese lo siguiente:|Acción |
| :------------|:-------|
| ¿Quiero usar el plan de llamadas de Microsoft como mi operador de telefonía? | Para obtener más información, consulta [sistema telefónico con planes de llamadas](calling-plan-landing-page.md).|
| ¿Debo usar mi propio operador de telefonía? | Para obtener más información, consulte [sistema telefónico con enrutamiento directo](direct-routing-landing-page.md).
|||


## <a name="additional-deployment-decisions"></a>Decisiones de implementación adicionales

Es posible que desee cambiar la configuración de lo siguiente, en función de las necesidades y la configuración de su organización:

- Correo de voz
- Identidad de llamadas
- Números de teléfono de Microsoft
- Planes de marcado
- Colas de llamadas
- Operadores automáticos

### <a name="voicemail"></a>Correo de voz

El buzón de voz de nube, basado en los servicios de buzón de voz de Azure, admite depósitos de buzón de voz solo y no admite sistemas de correo electrónico de terceros. El buzón de voz de nube incluye la transcripción del buzón de voz, que está habilitada para todos los usuarios de su organización de forma predeterminada. Las necesidades de su empresa pueden requerir que deshabilite la transcripción del buzón de voz para usuarios específicos o para todos los miembros de la organización.

|Pregúntese lo siguiente:|Acción |
|:------------|:-------|
| ¿Quiero habilitar el buzón de voz de nube? | Para los procedimientos de configuración de buzón de voz, consulte [configurar el buzón de voz en la nube](set-up-phone-system-voicemail.md).
| ¿Quiero habilitar la transcripción del buzón de voz para algunos o todos los usuarios? | Para desactivar la transcripción del buzón de voz, consulte [configurar directivas de buzón de voz en su organización](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</li></ul>|
|||

### <a name="calling-identity"></a>Identidad de llamadas

De forma predeterminada, todas las llamadas salientes usan el número de teléfono asignado como identidad de llamada (identificación de llamada). El destinatario de la llamada puede identificar rápidamente a la persona que llama y decidir si desea aceptar o rechazar la llamada.

|Pregúntese lo siguiente:|Acción |
|:------------|:-------|
|¿Quiero enmascarar o deshabilitar la identificación de llamadas? | Para cambiar o bloquear la identificación de llamadas, vea [establecer la identificación de llamadas de un usuario](set-the-caller-id-for-a-user.md). |
|||

### <a name="phone-numbers-from-microsoft"></a>Números de teléfono de Microsoft

Microsoft tiene dos tipos de números telefónicos disponibles: números de *suscriptor* (usuario), que se pueden asignar a los usuarios de su organización, y números de *servicio* , disponibles como números de servicio de pago y gratuitos, que tienen mayor capacidad de llamadas simultáneas que los números de suscriptor y que se pueden asignar a servicios como audioconferencias, operadores automáticos o colas de llamadas.

|Pregúntese lo siguiente:|Acción |
| :------------|:-------|
| ¿Qué ubicaciones de usuario necesitan números de teléfono nuevos de Microsoft? | Para obtener información sobre cómo obtener números de teléfono, vea [administrar números de teléfono para su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) y [obtener números de teléfono para los usuarios](getting-phone-numbers-for-your-users.md). 
| ¿Qué tipo de número de teléfono (suscriptor o servicio) necesito? | Para elegir el tipo de número de teléfono que necesita, vea [diferentes tipos de números de teléfono para los planes de llamadas](different-kinds-of-phone-numbers-used-for-calling-plans.md).
¿Cómo Porto números de teléfono existentes a teams?|Para obtener más información, consulte [transferir números de teléfono a Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).
|||

### <a name="dial-plans"></a>Planes de marcado

Un plan de marcado de la característica del sistema telefónico de Microsoft 365 u Office 365 es un conjunto de reglas de normalización que traducen números de teléfono marcados a un formato alternativo (por lo general, formato E. 164) para la autorización de llamadas y el enrutamiento de llamadas.

Para obtener más información acerca de los planes de marcado, vea [¿Qué son los planes de marcado?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans).

|Pregúntese lo siguiente:|Acción |
|:------------|:-------|
| ¿Mi organización necesita un plan de marcado personalizado? | Para determinar si necesita un plan de marcado personalizado, consulte [planear planes de marcado de inquilino](what-are-dial-plans.md#planning-for-tenant-dial-plans)|
¿Qué usuarios necesitan un plan de marcado personalizado y qué plan de marcado del espacio empresarial se va a asignar a cada usuario? | Para agregar usuarios a un plan de marcado personalizado en PowerShell, vea [crear y administrar planes de marcado](create-and-manage-dial-plans.md). |
|||

### <a name="call-queues"></a>Colas de llamadas

Las colas de llamadas en nube incluyen saludos que se usan cuando un usuario llama a un número de teléfono de su organización, la capacidad de poner automáticamente las llamadas en espera y la posibilidad de buscar el siguiente agente de llamada disponible para controlar la llamada mientras las personas que llaman escuchan música en espera. Puede crear una o varias colas de llamadas para su organización. 


|Pregúntese lo siguiente:|Acción |
|:------------|:-------|
| ¿Mi organización necesita colas de llamadas? | Para obtener más información, consulte [crear una cola de llamadas en la nube](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) y [configurar el sistema telefónico](setting-up-your-phone-system.md). |

### <a name="auto-attendants"></a>Operadores automáticos

Los operadores automáticos de la nube se pueden usar para crear un sistema de menús para la organización que permita a los autores de llamadas externos e internos desplazarse por un sistema de menús para ubicar y realizar llamadas a usuarios o departamentos de la empresa.

|Pregúntese lo siguiente:|Acción |
|:------------|:-------|
| ¿Mi organización necesita operadores automáticos? | Para obtener más información, vea [Qué son los operadores automáticos de la nube](what-are-phone-system-auto-attendants.md) y [configurar un operador automático de la nube](create-a-phone-system-auto-attendant.md). |

### <a name="devices"></a>Dispositivos

Para obtener más información sobre los dispositivos compatibles, vea lo siguiente:

- [Administrar sus dispositivos en Microsoft Teams](devices/device-management.md)
- [Teléfonos IP](https://docs.microsoft.com/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [Dispositivos de audio y vídeo USB](https://docs.microsoft.com/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [Comunicaciones inteligentes para dispositivos](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


