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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 'Obtenga más información sobre las características, la disponibilidad y cómo planificar y configurar el sistema telefónico de Microsoft para su empresa. '
ms.openlocfilehash: 32c094860ee5ff102a541062616e038cf2f37be6
ms.sourcegitcommit: 491c44b6a9b30faaf4d73394969f4a0587362830
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2020
ms.locfileid: "47820574"
---
# <a name="heres-what-you-get-with-phone-system"></a>Esto es lo obtiene con el Sistema telefónico

En este artículo se describen las características del sistema telefónico. Para obtener más información sobre cómo usar el sistema telefónico como sustitución de la central de conmutación (PBX) y las opciones para conectarse a la red de telefonía pública conmutada (RTC), consulte [Qué es el sistema telefónico](what-is-phone-system-in-office-365.md).

Los clientes están disponibles para PC, Mac y dispositivos móviles, que proporcionan características en dispositivos de tabletas y teléfonos móviles a PC y teléfonos IP de escritorio. Para obtener más información, consulte [obtener clientes de Microsoft Teams](get-clients.md).

 > [!Note]
> Para obtener más información sobre los sistemas telefónicos de los equipos en diferentes plataformas, consulte [características de Teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).
  
## <a name="phone-system-features"></a>Características del sistema telefónico

El sistema telefónico proporciona las siguientes características. A menos que se indique lo contrario, las características están disponibles tanto en los equipos como en Skype empresarial online.
  
|||
|:-----|:-----|
|**Característica de sistema telefónico** <br/> |**Descripción** <br/> |
|[Operadores automáticos en la nube](what-are-phone-system-auto-attendants.md) <br/> |Le permite crear un sistema de menús que permite a los autores de llamadas externos e internos ubicar y realizar o transferir llamadas a usuarios o departamentos de la empresa en su organización.  <br/> |
|[Colas de llamadas en la nube](create-a-phone-system-call-queue.md) <br/> |Le permite configurar cómo se administran las colas de llamadas para su organización: por ejemplo, configurar los saludos y la música en espera, busque el siguiente agente de llamada disponible para controlar la llamada y así sucesivamente.  <br/> |
|Música en espera | Reproduce la música predeterminada definida por el servicio cuando se coloca en espera una llamada externa de la red de telefonía pública conmutada (RTC). Esta característica funciona para las llamadas entre usuarios de RTC y entre equipos, además de las llamadas hechas a una cola de llamadas. Esta característica proporciona paridad de notificaciones en espera con otras plataformas. El administrador puede configurar esta característica, pero [actualmente solo mediante PowerShell](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps). La retención de música tampoco se admite en la transferencia Consultiva de una llamada RTC.|
|Iniciar/responder llamadas (por nombre y número)  <br/> |Permite a los usuarios contestar las llamadas entrantes con un toque y realizar llamadas salientes, ya sea marcando el número de teléfono completo o haciendo clic en un nombre en el cliente.  <br/> |
|[Opciones de desvío de llamadas y llamadas simultáneas](https://support.office.com/article/call-forwarding-call-groups-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) <br/> |Permite a los usuarios configurar reglas de reenvío para que las llamadas puedan llevarse a cabo en cualquier lugar, o desviar las llamadas a colegas o al buzón de voz.  <br/> |
|[Recoger la llamada grupal y reenviar al grupo](call-sharing-and-group-call-pickup.md) <br/> | Permite a los usuarios compartir llamadas entrantes con colegas para que los compañeros puedan responder llamadas que se produzcan mientras el usuario no está disponible. Menos interrupciones para los destinatarios que otras formas de uso compartido de llamadas (como el desvío de llamadas o las llamadas simultáneas), ya que los usuarios pueden configurar cómo desean recibir una notificación de una llamada compartida entrante. |
|[Transferir una llamada y una transferencia Consultiva](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0) <br/> |Permite a los usuarios transferir llamadas a otra persona. O bien, si necesitan abandonar su oficina pero quiere continuar con la conversación, pueden transferir las llamadas desde su equipo o teléfono IP a su teléfono móvil.  <br/> |
|[Transferir al buzón de voz llamada MID](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0) <br/> | Permite que los usuarios se transfieran al buzón de voz durante una llamada. |
|[Estacionar llamadas y recuperar](call-park-and-retrieve.md)  <br/> | Permite a los usuarios poner una llamada en espera en el servicio de Teams en la nube. Cuando se aparca una llamada, el servicio genera un código único para la recuperación de la llamada. El usuario que ha aparcado la llamada u otra persona puede usar ese código y una aplicación o dispositivo admitido para recuperar la llamada. <br/> |
|Llamar a un número de teléfono desde la búsqueda  <br/> | Permite a los usuarios llamar desde el cuadro de búsqueda usando el comando/call y especificando un nombre o un número. <br/> |
|[Identificador de llamada](how-can-caller-id-be-used-in-your-organization.md)  <br/> |Las llamadas desde dentro de la compañía muestran una identificación detallada de llamadas que extrae información del directorio corporativo, que muestra el identificador de la imagen y el puesto, en lugar de un número de teléfono. Para las llamadas de números de teléfono externos, se muestra la identificación de llamadas que proporciona el proveedor de servicios telefónicos. Si los números de teléfono externos son números secundarios en el directorio corporativo, se mostrará la información del directorio corporativo.  <br/> |
|Cambio de dispositivo  <br/> |Permite a los usuarios reproducir una llamada o una reunión en otro dispositivo HID que está conectado a teams. por ejemplo, si cambias de sus altavoces de PC a auriculares con micrófono.   <br/> |
|Enrutamiento de llamadas basado en presencia <br/> |Controla las comunicaciones entrantes con presencia, lo que permite al usuario bloquear todas las comunicaciones entrantes excepto las indicadas específicamente.  <br/> |
|[Teclado de marcado integrado](https://support.office.com/article/use-the-dial-pad-in-teams-27bc60b5-74c0-4e9c-808b-da4db9514d89) <br/> | Permite a los usuarios marcar por nombre o por número en cualquier lugar de la barra de búsqueda y en el teclado de marcado, lo que acelera el proceso de realizar llamadas salientes. <br/> |
|Llamadas federadas  <br/> |Permite a los usuarios conectarse, comunicarse y colaborar con usuarios de forma segura en inquilinos federados.  <br/> |
|[Realizar y recibir una videollamada](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42) <br/> | Si la cuenta del usuario está habilitada para las videollamadas, el usuario puede hacer videollamadas cara a cara con sus contactos. Todo lo que necesitan es una cámara, los altavoces y el micrófono de su equipo informático. Los usuarios también pueden usar auriculares con micrófono si su equipo no tiene un dispositivo de audio integrado.<br/> |
|[Buzón de voz de nube](set-up-phone-system-voicemail.md) <br/> | Cuando un usuario recibe un mensaje de voz, se envía a su buzón de Exchange como un correo electrónico con el mensaje de voz como datos adjuntos. Los usuarios pueden escuchar sus mensajes en sus teléfonos de escritorio certificados y en todos los equipos o aplicaciones de Skype empresarial. Se ha agregado la ayuda para la transcripción del buzón de voz a partir del 2017 de marzo y está habilitada de forma predeterminada para todas las organizaciones y todos los usuarios.   <br/> |
|[Configuración de usuario del buzón de voz en la nube](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US) <br/> | Permite a los usuarios configurar la configuración de sus clientes para los saludos del buzón de voz, reglas de contestador automático y idioma de saludo, incluidos los saludos fuera de la oficina.   |
|[Timbre secundario](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) <br/> | Los usuarios con varios dispositivos de altavoces conectados a su equipo pueden configurar un dispositivo secundario para que suene además de su altavoz predeterminado. Por ejemplo, un usuario con auriculares con micrófono conectados a los altavoces de escritorio y de PC puede elegir entre auriculares con micrófono y altavoces de escritorio cuando se recibe una llamada, de modo que no pierdan una llamada.  |
|[Alertas de timbre distintivo](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) (solo para equipos)<br/> |Permite que los usuarios elijan tonos de timbre por separado para las llamadas normales, las llamadas desviadas y las llamadas delegadas para que puedan distinguir el tipo de llamada.  <br/> |
|[Apariencia de línea compartida](shared-line-appearance.md) <br/> | Permite que los usuarios compartan su línea de teléfono para que otro usuario pueda hacer y recibir llamadas en su nombre.|
|[Ocupado en ocupado](teams-calling-policy.md) (solo en Teams) <br/> | Una directiva de llamadas que le permite configurar cómo se administran las llamadas entrantes cuando un usuario ya está en una llamada o conferencia o se hace una llamada en espera. La persona que llama escuchará una señal de ocupado cuando el destinatario de la llamada esté en el teléfono. El destinatario de la llamada recibe una notificación de llamada perdida, pero no puede contestar las llamadas entrantes. Esta característica está deshabilitada de forma predeterminada, pero puede activarla el administrador de inquilinos. |
|[Bloqueo de llamadas](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US) <br/> | Permite a los usuarios agregar números de teléfono (RTC) a una lista de bloqueados para que la siguiente llamada de ese número esté bloqueada para que no suene al usuario.|
|[Teléfonos de área común](set-up-common-area-phones.md) <br/> | Por lo general, un teléfono de área común se coloca en un área como una sala de recepción o una sala de conferencias que está disponible para varias personas. Los teléfonos de área común se configuran como dispositivos en lugar de usuarios y pueden iniciar sesión automáticamente en una red.|
|[Compatibilidad con omisión de medios](direct-routing-plan-media-bypass.md) (solo para equipos de enrutamiento directo) <br/> | Para un mejor rendimiento, los medios se mantienen entre el controlador de borde de sesión (SBC) y el cliente, en lugar de enviarlo a través del sistema telefónico de Microsoft. |


## <a name="availability-in-gcc-high-and-dod-clouds"></a>Disponibilidad en las nubes de alto y DoD de GCC
<a name="bkmk_setup"> </a>

Las siguientes capacidades aún no están disponibles en las nubes de GCC High y DoD. 
- [Configuración de llamadas para timbre secundario, buzón de voz y delegación mejorada](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)
- [Transferir al buzón de voz llamada MID](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)
- Llamar a un número de teléfono desde la barra de búsqueda
- Música en espera
- Búsqueda de números invertida de Azure AD

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

  
 
