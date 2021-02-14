---
title: Esto es lo obtiene con el Sistema telefónico
ms.reviewer: ''
author: CarolynRowe
ms.author: crowe
manager: serdars
msreviewer: jastarck, makolomi
ms.topic: conceptual
ms.assetid: bc9756d1-8a2f-42c4-98f6-afb17c29231c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 'Obtenga información sobre las características, la disponibilidad y cómo planear y configurar el sistema telefónico de Microsoft para su empresa. '
ms.openlocfilehash: b3a3da0a2cfd8038b3af84352c754c9014a1ad6c
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030406"
---
# <a name="heres-what-you-get-with-phone-system"></a>Esto es lo obtiene con el Sistema telefónico

En este artículo se describen las características del sistema telefónico. Para obtener más información sobre cómo usar Sistema telefónico como su sustitución de la central de conmutación (PBX) y las opciones para conectarse a la red telefónica conmutada (RTC), consulte ¿Qué es el sistema [telefónico?](what-is-phone-system-in-office-365.md)

Los clientes están disponibles para PC, Mac y móvil, que proporciona características en dispositivos desde tabletas y teléfonos móviles a PC y teléfonos IP de escritorio. Para obtener más información, [consulte Obtener clientes para Microsoft Teams.](get-clients.md)

 > [!Note]
> Para obtener más información sobre los sistemas telefónicos de Teams en distintas plataformas, consulte [Características de Teams por plataforma.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)
  
## <a name="phone-system-features"></a>Características del sistema telefónico

Sistema telefónico proporciona las siguientes características. A menos que se indique lo contrario, las características están disponibles tanto en Teams como en Skype Empresarial Online.
  
|||
|:-----|:-----|
|**Característica sistema telefónico** <br/> |**Descripción** <br/> |
|[Operadores automáticos en la nube](what-are-phone-system-auto-attendants.md) <br/> |Le permite crear un sistema de menús que permite a los autores de llamadas internos y externos localizar y realizar o transferir llamadas a usuarios de la empresa o departamentos de su organización.  <br/> |
|[Colas de llamadas en la nube](create-a-phone-system-call-queue.md) <br/> |Le permite configurar cómo se administran las colas de llamadas para su organización: por ejemplo, configurar saludos y música en espera, buscar el siguiente agente de llamada disponible para que se encarga de la llamada, y así sucesivamente.  <br/> |
|Música en espera | Reproduce música predeterminada definida por el servicio cuando una llamada externa de la red telefónica conmutada (RTC) pública se pone en espera. Esta característica funciona para las llamadas rtc a equipos uno a uno, además de las llamadas realizadas a una cola de llamadas. Esta característica ofrece paridad de notificaciones en espera con otras plataformas. Esta característica es configurable por el administrador, pero [actualmente solo a través de PowerShell.](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps) La música en espera tampoco es compatible con la transferencia consultiva de una llamada RTC.|
|Iniciar/responder llamadas (por nombre y número)  <br/> |Permite a los usuarios responder llamadas entrantes con un toque y realizar llamadas salientes ya sea marcando el número de teléfono completo o haciendo clic en un nombre en el cliente.  <br/> |
|[Opciones de reenvío de llamadas y llamadas simultáneas](https://support.office.com/article/call-forwarding-call-groups-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) <br/> |Permite a los usuarios configurar reglas de reenvío para que las llamadas puedan ir a cualquier lugar, o bien las llamadas se pueden reenviar a colegas o al correo de voz.  <br/> |
|[Recogida de llamadas grupales y reenvío al grupo](call-sharing-and-group-call-pickup.md) <br/> | Permite a los usuarios compartir las llamadas entrantes con compañeros para que estos puedan responder a las llamadas que se produzcan mientras el usuario no esté disponible. Menos perturbador para los destinatarios que otras formas de uso compartido de llamadas (como el reenvío de llamadas o llamadas simultáneas) porque los usuarios pueden configurar cómo quieren que se les notifique de una llamada compartida entrante. |
|[Transferir una llamada y una transferencia consultiva](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0) <br/> |Permite que los usuarios transfieren llamadas a otra persona. O bien, si tienen que salir de la oficina pero desean continuar con la conversación, pueden transferir las llamadas desde su teléfono IP o PC a su teléfono móvil.  <br/> |
|[Transferir al correo de voz durante una llamada](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0) <br/> | Permite a los usuarios transferir al correo de voz durante una llamada. |
|[Estacionar llamadas y recuperar](call-park-and-retrieve.md)  <br/> | Permite a los usuarios poner una llamada en espera en el servicio Teams en la nube. Cuando una llamada está estacionada, el servicio genera un código único para la recuperación de la llamada. El usuario que estacionó la llamada o cualquier otra persona puede usar ese código y una aplicación o dispositivo compatible para recuperar la llamada. <br/> |
|Llamar al número de teléfono desde la búsqueda  <br/> | Permite a los usuarios realizar una llamada desde el cuadro de búsqueda mediante el comando /call y especificar un nombre o un número. <br/> |
|[Identificador de llamada](how-can-caller-id-be-used-in-your-organization.md)  <br/> |Las llamadas desde dentro de la empresa muestran un identificador de llamada detallado que extrae información del directorio corporativo y muestra la identificación de la imagen y el puesto en lugar de solo un número de teléfono. Para las llamadas desde números de teléfono externos, se muestra el identificador de llamada proporcionado por el proveedor de servicios telefónicos. Si los números de teléfono externos son números secundarios en el directorio corporativo, se mostrará la información del directorio corporativo.  <br/> |
|Cambio de dispositivo  <br/> |Permite a los usuarios reproducir una llamada o una reunión en otro dispositivo HID conectado a Teams; por ejemplo, cambiar de los altavoces de su PC a unos auriculares.   <br/> |
|Enrutamiento de llamadas basado en presencia <br/> |Controla las comunicaciones entrantes con la presencia, lo que permite al usuario bloquear todas las comunicaciones entrantes excepto aquellas indicadas específicamente.  <br/> |
|[Teclado de marcado integrado](https://support.office.com/article/use-the-dial-pad-in-teams-27bc60b5-74c0-4e9c-808b-da4db9514d89) <br/> | Permite a los usuarios marcar por nombre o número en cualquier lugar de la barra de búsqueda y en el teclado de marcado, lo que acelera el proceso de realizar llamadas salientes. <br/> |
|Llamadas federadas  <br/> |Permite a los usuarios conectarse, comunicarse y colaborar con los usuarios de inquilinos federados de forma segura.  <br/> |
|[Realizar y recibir una videollamada](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42) <br/> | Si la cuenta del usuario está habilitada para videollamadas, el usuario podrá realizar videollamadas cara a cara con sus contactos. Solo necesitan una cámara, los altavoces y el micrófono de su PC. Los usuarios también pueden usar auriculares si su equipo no tiene un dispositivo de audio integrado.<br/> |
|[Correo de voz en la nube](set-up-phone-system-voicemail.md) <br/> | Cuando un usuario recibe un correo de voz, se entrega a su buzón de Exchange como un correo electrónico con el mensaje de correo de voz como datos adjuntos. Los usuarios pueden escuchar sus mensajes en su teléfono de escritorio certificado y en todas las aplicaciones de Teams o Skype Empresarial. La compatibilidad de la transcripción del correo de voz se agregó en marzo de 2017 y está habilitada de forma predeterminada para todas las organizaciones y usuarios.   <br/> |
|[Configuración de usuario del correo de voz en la nube](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US) <br/> | Permite a los usuarios configurar las opciones de cliente para los saludos del correo de voz, las reglas de respuesta de llamadas y el idioma del saludo, incluidos los saludos de fuera de la oficina.   |
|[Timbre secundario](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) <br/> | Los usuarios con varios dispositivos de altavoces conectados a su EQUIPO pueden configurar un dispositivo secundario para que suene además de su altavoz predeterminado. Por ejemplo, un usuario con unos auriculares conectados al equipo y altavoces de escritorio puede elegir que los auriculares y los altavoces de escritorio suene cuando se produce una llamada para que no se pierdan una llamada.  |
|[Alertas de tono distintivo](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) (solo Teams)<br/> |Permite a los usuarios elegir tonos diferentes para las llamadas normales, las llamadas desviadas y las llamadas delegadas, de modo que puedan distinguir el tipo de llamada.  <br/> |
|[Apariencia de línea compartida](shared-line-appearance.md) <br/> | Permite a los usuarios compartir su línea telefónica para que otro usuario pueda realizar y recibir llamadas en su nombre.|
|[Ocupado en Ocupado](teams-calling-policy.md) (solo equipos) <br/> | Una directiva de llamada que le permite configurar cómo se administran las llamadas entrantes cuando un usuario ya está en una llamada o conferencia o tiene una llamada en espera. El autor de la llamada escuchará una señal de ocupado cuando el destinatario ya esté en el teléfono. El destinatario de la llamada recibe una notificación de llamada perdida, pero no puede responder a las llamadas entrantes. Esta característica está deshabilitada de forma predeterminada, pero puede ser activada por el administrador de inquilinos. |
|[Bloqueo de llamadas](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US) <br/> | Permite a los usuarios agregar números de teléfono (RTC) a una lista bloqueada para que la siguiente llamada de ese número se bloquee y no suene.|
|[Teléfonos de área comunes](set-up-common-area-phones.md) <br/> | Normalmente, un teléfono de área común se coloca en un área como una sala de espera o una sala de conferencias para que esté disponible para varias personas. Los teléfonos de área comunes se establecen como dispositivos en lugar de usuarios y pueden iniciar sesión automáticamente en una red.|
|[Soporte de omisión de medios](direct-routing-plan-media-bypass.md) (solo para enrutamiento directo de Teams) <br/> | Para un mejor rendimiento, los medios se mantienen entre el controlador de borde de sesión (SBC) y el cliente en lugar de enviarlos a través del sistema telefónico de Microsoft. |


## <a name="availability-in-gcc-high-and-dod-clouds"></a>Disponibilidad en nubes GCC High y DoD
<a name="bkmk_setup"> </a>

Las siguientes funcionalidades aún no están disponibles en GCC High y DoD Clouds. 
- [Configuración de llamadas para timbre secundario, correo de voz y delegación mejorada](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)
- [Transferir al correo de voz durante una llamada](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)
- Llamar al número de teléfono desde la barra de búsqueda
- Música en espera
- Búsqueda inversa de números de Azure AD

## <a name="related-topics"></a>Temas relacionados

- [¿Qué es el Sistema telefónico?](what-is-phone-system-in-office-365.md)
- [Voz en la nube de Microsoft Teams](cloud-voice-landing-page.md)
- [Configurar el Sistema telefónico](setting-up-your-phone-system.md)
- [¿Qué plan de llamada es adecuado para usted?](calling-plan-landing-page.md)
- [Enrutamiento directo del Sistema telefónico](direct-routing-landing-page.md)
- [Supervisar y administrar la calidad de las llamadas](monitor-call-quality-qos.md)
- [Licencias complementarias de Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
- [Precios de Sistema telefónico](https://products.office.com/microsoft-teams/voice-calling#requirements)
- [Teams para infraestructura de escritorio virtualizada con llamadas y reuniones](teams-for-vdi.md#teams-on-vdi-with-calling-and-meetings)

  
 
