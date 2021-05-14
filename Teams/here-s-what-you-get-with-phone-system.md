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
description: 'Obtenga información sobre las características, la disponibilidad y cómo planear y configurar Teléfono Microsoft sistema para su empresa. '
ms.openlocfilehash: eba13d07c41af8b449d0164542c4d241b1b54f66
ms.sourcegitcommit: 272e8cf0075a566f055801433c9eb0313050530f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2021
ms.locfileid: "52486364"
---
# <a name="heres-what-you-get-with-phone-system"></a>Esto es lo obtiene con el Sistema telefónico

En este artículo se describen Sistema telefónico características. Para obtener más información sobre el uso de Sistema telefónico Exchange como su reemplazo de pbx (PBX) de la rama privada y las opciones para conectarse a la red telefónica conmutada (RTC), vea Qué Sistema telefónico [.](what-is-phone-system-in-office-365.md)

Los clientes están disponibles para PC, Mac y dispositivos móviles, lo que proporciona características en dispositivos desde tabletas y teléfonos móviles hasta equipos PC y teléfonos IP de escritorio. Para obtener más información, vea [Obtener clientes para Microsoft Teams](get-clients.md).

 > [!Note]
> Para obtener más información Teams sistemas telefónicos en diferentes plataformas, vea [Teams características por plataforma.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)
  
## <a name="phone-system-features"></a>Sistema telefónico características

Sistema telefónico proporciona las siguientes características. A menos que se indique lo contrario, las características están disponibles tanto en Teams como Skype Empresarial online.
  
|||
|:-----|:-----|
|**Sistema telefónico característica de Sistema telefónico de datos** <br/> |**Descripción** <br/> |
|[Operadores automáticos en la nube](what-are-phone-system-auto-attendants.md) <br/> |Le permite crear un sistema de menús que permite a los autores de llamadas externos e internos localizar y realizar o transferir llamadas a usuarios o departamentos de la empresa de su organización.  <br/> Tenga en cuenta *que los usuarios no* necesitan estar habilitados para recibir llamadas del operador automático. |
|[Colas de llamadas en la nube](create-a-phone-system-call-queue.md) <br> |Le permite configurar cómo se administran las colas de llamadas para su organización: por ejemplo, configurar saludos y música en espera, buscar el siguiente agente de llamada disponible para administrar la llamada, y así sucesivamente.  <br/> Tenga en cuenta que *los usuarios* necesitan estar habilitados para recibir llamadas desde una cola de llamadas.|
|Música en espera | Reproduce música predeterminada definida por el servicio cuando una llamada externa de la red telefónica conmutada (RTC) está en espera. Esta característica funciona para llamadas RTC a Teams llamadas, además de las llamadas realizadas a una cola de llamadas. Esta característica proporciona paridad de notificaciones en espera con otras plataformas. Esta característica es configurable por el administrador, pero [actualmente solo a través de PowerShell.](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps) La música de retención tampoco es compatible con la transferencia consultiva de una llamada RTC.|
|Iniciar/responder llamadas (por nombre y número)  <br/> |Permite a los usuarios responder llamadas entrantes con un toque y realizar llamadas salientes marcando el número de teléfono completo o haciendo clic en un nombre en el cliente.  <br/> |
|[Opciones de reenvío de llamadas y llamada simultánea](https://support.office.com/article/call-forwarding-call-groups-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) <br/> |Permite a los usuarios configurar reglas de reenvío para que las llamadas puedan ir con ellas a cualquier lugar, o las llamadas se pueden reenviar a compañeros o al correo de voz.  <br/> |
|[Recogida de llamadas grupales y reenvío al grupo](call-sharing-and-group-call-pickup.md) <br/> | Permite a los usuarios compartir llamadas entrantes con compañeros de trabajo para que los compañeros puedan responder a las llamadas que se producen mientras el usuario no está disponible. Menos perjudicial para los destinatarios que otras formas de uso compartido de llamadas (como el reenvío de llamadas o la llamada simultánea) porque los usuarios pueden configurar cómo quieren recibir una notificación de una llamada compartida entrante. |
|[Transferir una llamada y una transferencia consultiva](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0) <br/> |Permite a los usuarios realizar transferencias de llamadas a otra persona. O bien, si necesitan abandonar su oficina pero quieren continuar la conversación, pueden transferir las llamadas desde su PC o teléfono IP a su teléfono móvil.  <br/> Tenga en cuenta que *los usuarios* necesitan tener habilitada la voz para recibir llamadas transferidas de otro usuario. |
|[Transferir al correo de voz a mitad de llamada*](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0) <br/> | Permite a los usuarios transferir al correo de voz durante una llamada. |
|[Estacionar llamadas y recuperar](call-park-and-retrieve.md)  <br/> | Permite a los usuarios realizar una llamada en espera en el Teams en la nube. Cuando una llamada está estacionada, el servicio genera un código único para la recuperación de llamadas. El usuario que estacionó la llamada u otra persona puede usar ese código y una aplicación o dispositivo compatible para recuperar la llamada. <br/> |
|Llamar al número de teléfono desde la búsqueda  <br/> | Permite a los usuarios realizar una llamada desde el cuadro de búsqueda mediante el comando /call y especificar un nombre o un número. <br/> |
|[Identificador de llamada](how-can-caller-id-be-used-in-your-organization.md)  <br/> |Las llamadas desde dentro de la compañía muestran un id. de llamada detallado que extrae información del directorio corporativo, que muestra el id. de imagen y el puesto de trabajo en lugar de solo un número de teléfono. Para las llamadas de números de teléfono externos, se muestra el identificador de llamada proporcionado por el proveedor de servicios telefónicos. Si los números de teléfono externos son números secundarios en el directorio corporativo, se mostrará la información del directorio corporativo.  <br/> |
|Cambio de dispositivo  <br/> |Permite a los usuarios reproducir una llamada o reunión en otro dispositivo HID conectado a Teams; por ejemplo, cambiar de los altavoces de su PC a unos auriculares.   <br/> |
|Enrutamiento de llamadas basado en presencia <br/> |Controla las comunicaciones entrantes con presencia, lo que permite al usuario bloquear todas las comunicaciones entrantes excepto las indicadas específicamente.  <br/> |
|[Teclado de marcado integrado](https://support.office.com/article/use-the-dial-pad-in-teams-27bc60b5-74c0-4e9c-808b-da4db9514d89) <br/> | Permite a los usuarios marcar por nombre o por número en cualquier lugar de la barra de búsqueda y en el teclado de marcado, acelerando el proceso de realizar llamadas salientes. <br/> |
|Llamadas federadas  <br/> |Permite a los usuarios conectarse, comunicarse y colaborar de forma segura con los usuarios de inquilinos federados.  <br/> |
|[Realizar y recibir una videollamada](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42) <br/> | Si la cuenta del usuario está habilitada para videollamadas, el usuario puede realizar videollamadas cara a cara con sus contactos. Todo lo que necesitan es una cámara, los altavoces y el micrófono de su equipo. Los usuarios también pueden usar auriculares si su equipo no tiene un dispositivo de audio integrado.<br/> |
|[Correo de voz en la nube*](set-up-phone-system-voicemail.md) <br/> | Cuando un usuario recibe un correo de voz, se entrega a su buzón de Exchange como correo electrónico con el mensaje de correo de voz como datos adjuntos. Los usuarios pueden escuchar sus mensajes en su teléfono de escritorio certificado y en todas Teams o Skype Empresarial aplicaciones. El soporte para la transcripción del correo de voz se ha agregado a partir de marzo de 2017 y está habilitado de forma predeterminada para todas las organizaciones y usuarios.   <br/> |
|[Configuración del usuario del correo de voz en la nube*](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US) <br/> | Permite a los usuarios configurar la configuración del cliente para saludos de correo de voz, reglas de respuesta de llamadas e idioma de saludo, incluidos los saludos fuera de la oficina.   |
|[Timbre secundario](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) <br/> | Los usuarios con varios dispositivos de altavoz conectados a su PC pueden elegir configurar un dispositivo secundario para que suene además de su altavoz predeterminado. Por ejemplo, un usuario con auriculares conectados al equipo y altavoces de escritorio puede elegir que los altavoces de auriculares y de escritorio suene cuando se produce una llamada para que no se pierda una llamada.  |
|[Alertas de anillo distintivo](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) (solo Teams)<br/> |Permite a los usuarios elegir tonos separados para llamadas normales, llamadas reenviadas y llamadas delegadas para que puedan distinguir el tipo de llamada.  <br/> |
|[Apariencia de línea compartida](shared-line-appearance.md) <br/> | Permite a los usuarios compartir su línea telefónica para que otro usuario pueda realizar y recibir llamadas en su nombre.|
|[Ocupado en Ocupado](teams-calling-policy.md) (solo Teams) <br/> | Una directiva de llamadas que le permite configurar cómo se administran las llamadas entrantes cuando un usuario es: <ul><li>en una llamada </li><li>en una conferencia</li><li>tiene una llamada en espera. </li></ul> El autor de la llamada recibirá una de las siguientes respuestas: <ul><li>escuchar una señal ocupada cuando el destinatario está en el teléfono</li> <li>se enruta en consecuencia a la configuración sin responder del usuario. Una opción permite al autor de la llamada dejar un correo de voz para el usuario que ya está en una llamada.</li></ul> El destinatario recibe una notificación de llamada perdida, pero no puede responder a las llamadas entrantes. Esta característica está deshabilitada de forma predeterminada, pero puede ser activada por el administrador de inquilinos.|
|[Bloqueo de llamadas](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US) <br/> | Permite a los usuarios agregar números de teléfono (RTC) a una lista bloqueada para que la siguiente llamada de ese número no suene al usuario.|
|[Teléfonos de área común](set-up-common-area-phones.md) <br/> | Normalmente, un teléfono de área común se coloca en un área como una sala de espera o una sala de conferencias, lo que hace que esté disponible para varias personas. Los teléfonos de área común están configurados como dispositivos en lugar de como usuarios y pueden iniciar sesión automáticamente en una red.|
|[Soporte de omisión de](direct-routing-plan-media-bypass.md) medios (solo Teams enrutamiento directo) <br/> | Para un mejor rendimiento, los medios se mantienen entre el controlador de borde de sesión (SBC) y el cliente en lugar de enviarlo a través del sistema Teléfono Microsoft sesión. |


\* Los usuarios no necesitan tener habilitada la voz para usar las características del correo de voz.

## <a name="availability-in-gcc-high-and-dod-clouds"></a>Disponibilidad en GCC nubes Altas y DoD
<a name="bkmk_setup"> </a>

Las siguientes funcionalidades aún no están disponibles en GCC nubes altas y doD. 

- [Configuración de llamadas para timbre secundario, correo de voz y delegación mejorada](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)
- [Transferir al correo de voz a mitad de llamada](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)
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
- [Licencias complementarias de Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Precios de Sistema telefónico](https://products.office.com/microsoft-teams/voice-calling#requirements)
- [Teams infraestructura de escritorio virtualizada con llamadas y reuniones](teams-for-vdi.md#teams-on-vdi-with-calling-and-meetings)
