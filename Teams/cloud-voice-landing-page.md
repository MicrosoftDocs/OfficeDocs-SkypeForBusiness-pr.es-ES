---
title: Voz en la nube de Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
description: Página de inicio a la implementación de voz en la nube en los equipos
appliesto:
- Microsoft Teams
ms.openlocfilehash: 47c534eba93c6f5af21a75fa20b5015fac00c674
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198374"
---
# <a name="cloud-voice-in-microsoft-teams"></a>Voz en la nube de Microsoft Teams

Ha completado la [Introducción](get-started-with-teams-quick-start.md). Ha implementado Teams con [chat, equipos, canales y aplicaciones](deploy-chat-teams-channels-microsoft-teams-landing-page.md) en toda la organización. Es posible que haya implementado [conferencia & de las reuniones](deploy-meetings-microsoft-teams-landing-page.md). Ahora está listo para agregar funciones de voz en la nube para los usuarios. 

En la nube voz proporciona capacidades de conmutación (PBX) y opciones para la conexión a la red telefónica pública conmutada (RTC).

En este artículo le ayudará a decidir si necesita cambiar cualquiera de las opciones de voz de forma predeterminada en la nube, según el perfil de su organización y los requisitos empresariales, a continuación, le guiará a través de cada cambio. Nos hemos dividir en dos grupos, empezando con el conjunto principal de [los cambios que es más probable que realizar](#core-deployment-decisions)la configuración. El segundo grupo incluye las [opciones adicionales](#additional-deployment-decisions) que puede que quiera configurar, según las necesidades de su organización.

Se recomienda que todas las organizaciones funcionan a través de las decisiones principales y, a continuación, si su organización tiene requisitos adicionales, revisión la siguiente (en inglés).



## <a name="learn-more-about-cloud-voice"></a>Encontrará más información acerca de voz en la nube

Los artículos siguientes proporcionan más información sobre la implementación y uso de las características de voz de la nube en los equipos:

- [Sistema telefónico en Office 365](what-is-phone-system-in-office-365.md)
- [Sistema telefónico con planes de llamada](calling-plan-landing-page.md)
- [Enrutamiento directo del Sistema telefónico](direct-routing-landing-page.md)
- [Implementación de voz en la nube](cloud-voice-deployment.md)
- [Soluciones de telefonía de Microsoft](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions)
- Vea la sesión siguiente para obtener más información sobre el sistema telefónico: [Introducción al sistema de teléfono en los equipos de Microsoft](https://aka.ms/teams-phone-system)


## <a name="core-deployment-decisions"></a>Decisiones de implementación principales

Estas son las opciones que la mayoría de organizaciones cambia (si la configuración predeterminada de Teams no sirve para la organización).

## <a name="phone-system-office-365"></a>Sistema telefónico (Office 365)

Sistema telefónico es la tecnología de Microsoft para habilitar el control de llamadas y las capacidades de conmutación (PBX) en la nube de Office 365. Sistema telefónico permite reemplazar el sistema de conmutación (PBX) existente con un conjunto de características que se entregan directamente desde Office 365 y estrechamente integrados en la experiencia de productividad de la compañía en la nube.


|Pregúntese lo siguiente:|Acción |
|:------------|:-------|
|¿En qué oficinas o ubicaciones de usuario se implementar sistema telefónico? |Para obtener más información acerca del sistema de teléfono, vea [¿Qué es el sistema telefónico en Office 365](what-is-phone-system-in-office-365.md).</li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a>Conexión pública conmutada red telefónica (RTC)

Para conectar el sistema telefónico a la red telefónica pública conmutada (RTC) para que los usuarios pueden realizar llamadas telefónicas todo el mundo, dispone de opciones en función de sus necesidades empresariales.  Hágase lo siguiente:


|Pregúntese lo siguiente:|Acción |
| :------------|:-------|
| ¿Desea que se utilizará al llamar a planeación de Microsoft como mi portadora de telefonía? | Para obtener más información, vea [Sistema de teléfono con planes de llamada](calling-plan-landing-page.md).|
| ¿Es necesario usar mi propia portadora de telefonía? | Para obtener más información, vea [Sistema de teléfono con el enrutamiento directo](direct-routing-landing-page.md).
|||


## <a name="additional-deployment-decisions"></a>Decisiones de implementación adicionales

Es posible que desee cambiar la configuración de los siguientes valores, en función de las necesidades de su organización y la configuración:

- Correo de voz
- Identidad de llamada
- Números de teléfono de Microsoft
- Planes de marcado
- Colas de llamadas
- Operadores automáticos

### <a name="voicemail"></a>Correo de voz

Correo de voz en la nube, con tecnología de servicios de correo de voz de Azure, es compatible con depósitos de correo de voz a los buzones de Exchange y no es compatible con sistemas de correo electrónico de otro fabricante. Correo de voz en la nube incluye transcripción de correo de voz, que está habilitado para todos los usuarios de la organización de forma predeterminada. Las necesidades de negocio pueden requerir que deshabilite la transcripción de correo de voz para usuarios específicos o todos los usuarios en toda la organización.

|Pregúntese lo siguiente:|Acción |
|:------------|:-------|
| ¿Desea habilitar el correo de voz en la nube? | Para los procedimientos de configuración de correo de voz, vea [Configurar el correo de voz en la nube](set-up-phone-system-voicemail.md).
| ¿Desea habilitar la transcripción de correo de voz para todos o algunos de Mis usuarios? | Para desactivar la transcripción de correo de voz, consulte [configuración de directivas de correo de voz en su organización](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</li></ul>|
|||

### <a name="calling-identity"></a>Identidad de llamada

De forma predeterminada, todas las llamadas salientes utilizan el número de teléfono asignado como llamada identidad (identificador de autor de la llamada). El destinatario de la llamada puede identificar rápidamente a la persona que llama y decidir si desea aceptar o rechazar la llamada.

|Pregúntese lo siguiente:|Acción |
|:------------|:-------|
|¿Desea enmascarar o deshabilitar el identificador de autor de la llamada? | Para cambiar o bloquear el identificador de autor de la llamada, vea [establecer el identificador de autor de la llamada de un usuario](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user). |
|||

### <a name="phone-numbers-from-microsoft"></a>Números de teléfono de Microsoft

Microsoft tiene dos tipos de números de teléfono disponibles: números de *suscriptor* (usuario), que se pueden asignar a los usuarios de su organización y números de *servicio* , disponibles como números de pago y los números de un servicio gratuito, que tienen mayor llamadas simultáneas capacidad de números de suscriptor y se pueden asignar a servicios, como conferencias de Audio, operadores automáticos o colas de llamadas.

|Pregúntese lo siguiente:|Acción |
| :------------|:-------|
| ¿Qué ubicaciones de usuario necesitan nuevos números de teléfono de Microsoft? | Para obtener información acerca de cómo obtener los números de teléfono, vea [administrar los números de teléfono para su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) y [los números de teléfono de introducción para los usuarios](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users). 
| ¿Qué tipo de número de teléfono (suscriptor o servicio) es necesario? | Para ayudarle a elegir el tipo de número de teléfono que necesita, vea [distintos tipos de números de teléfono utilizados para llamar a los planes](different-kinds-of-phone-numbers-used-for-calling-plans.md).
¿Cómo puerto existente los números de teléfono a Office 365?|Para obtener más información, vea [transferir los números de teléfono para Office 365](transfer-phone-numbers-to-office-365.md).
|||

### <a name="dial-plans"></a>Planes de marcado

Un plan de marcado de la característica de sistema telefónico de Office 365 es un conjunto de reglas de normalización que traducir marca números de teléfono en un formato alternativo (normalmente, el formato E.164) para la autorización de llamadas y el enrutamiento de llamadas.

Para obtener más información acerca de los planes de marcado, vea [¿Qué son los planes de marcado?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans).

|Pregúntese lo siguiente:|Acción |
|:------------|:-------|
| ¿Mi organización necesita un plan de marcado personalizado? | Para ayudar a determinar si necesita un plan de marcado personalizado, consulte [Planning for inquilino planes de marcado](what-are-dial-plans.md#planning-for-tenant-dial-plans)|
¿Qué usuarios necesitan un plan de marcado personalizado y qué plan de marcado del espacio empresarial se va a asignar a cada usuario? | Para agregar usuarios a un plan de marcado personalizado en PowerShell, vea [crear y administrar planes de marcado](create-and-manage-dial-plans.md). |
|||

### <a name="call-queues"></a>Colas de llamadas

Colas de llamada de nube incluyen el saludo que se usa cuando alguien llama a un número de teléfono para su organización, la capacidad de poner automáticamente las llamadas en espera y la capacidad de búsqueda para el siguiente agente de llamada disponibles controlar la llamada mientras las personas que son de llamada escucha música en espera. Puede crear una o varias colas de llamadas para su organización. 


|Pregúntese lo siguiente:|Acción |
|:------------|:-------|
| ¿Mi organización necesitan llamar a colas? | Para obtener más información, vea [crear una cola de llamada en la nube](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) y la [Configuración del sistema de teléfono](setting-up-your-phone-system.md). |

### <a name="auto-attendants"></a>Operadores automáticos

Operadores automáticos en la nube se pueden usar para crear un sistema de menús para la organización que permite externo y mover los autores de llamadas internas a través de un sistema de menús para localizar y colocar o transferir las llamadas a los usuarios de la compañía o los departamentos de la organización.

|Pregúntese lo siguiente:|Acción |
|:------------|:-------|
| ¿Necesita mi organización automáticos? | Para obtener más información, vea [¿Cuáles son los operadores automáticos de la nube](what-are-phone-system-auto-attendants.md) y [configurar un operador automático de la nube](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json). |

### <a name="devices"></a>Dispositivos

Para obtener más información sobre los dispositivos admitidos, consulte lo siguiente:

- [Administrar sus dispositivos en Microsoft Teams](device-management.md)
- [Teléfonos IP](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [Dispositivos de audio y vídeo USB](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [Comunicaciones inteligentes para dispositivos](https://products.office.com/en-gb/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


