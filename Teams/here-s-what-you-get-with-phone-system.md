---
title: Esto es lo obtiene con el Sistema telefónico
ms.reviewer: ''
author: CarolynRowe
ms.author: crowe
manager: serdars
msreviewer: jastarck, roykuntz
ms.topic: conceptual
ms.assetid: bc9756d1-8a2f-42c4-98f6-afb17c29231c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 'Obtén información sobre las características, la disponibilidad y cómo planear y configurar Microsoft Phone System para tu empresa. '
ms.openlocfilehash: ccc931bd15e511903715ca328a142eb4da313dea
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2022
ms.locfileid: "68584791"
---
# <a name="heres-what-you-get-with-phone-system"></a>Esto es lo obtiene con el Sistema telefónico

En este artículo se describen las características del sistema telefónico. Para obtener más información sobre el uso del sistema telefónico como sustitución de la central de conmutación (PBX) y las opciones para conectarse a la red telefónica conmutada (RTC), consulte [¿Qué es el sistema telefónico](what-is-phone-system-in-office-365.md)?.

Los clientes están disponibles para PC, Mac y dispositivos móviles, que proporciona características en dispositivos, desde tabletas y teléfonos móviles hasta pc y teléfonos IP de escritorio. Para obtener más información, consulte [Obtener clientes para Microsoft Teams](get-clients.md).

 > [!Note]
> Para obtener más información sobre los sistemas telefónicos de Teams en distintas plataformas, consulte [Características de Teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

Para usar las características del sistema telefónico, la organización debe tener una licencia de Sistema telefónico. Para obtener más información sobre las licencias, vea [Licencias complementarias de Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

Tenga en cuenta que la mayoría de las características requieren que asigne la licencia de Sistema telefónico y asegúrese de que los usuarios estén "habilitados para voz". Para asignar la licencia, use el [cmdlet Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment?view=teams-ps) y establezca el parámetro **EnterpriseVoiceEnabled** en $true. Algunas características, como el operador automático de la nube, no requieren que un usuario tenga habilitada la voz. Las excepciones se indican en la tabla siguiente.
  
## <a name="phone-system-features"></a>Características del sistema telefónico

Sistema telefónico ofrece las siguientes características.
  
|Característica del sistema telefónico  |Descripción |
|:-----|:-----|
|[Operadores automáticos en la nube](what-are-phone-system-auto-attendants.md)  |Le permite crear un sistema de menús que permita a los autores de llamadas internos y externos localizar y realizar o transferir llamadas a usuarios o departamentos de la empresa de su organización.  <br/> Tenga en cuenta *que no es* necesario que los usuarios tengan habilitada la voz para recibir llamadas del operador automático marcando por nombre, marcando por búsqueda en el directorio de números. *Los usuarios* deben tener habilitada la voz para recibir llamadas de las opciones de menú del operador automático. |
|[Colas de llamadas en la nube](create-a-phone-system-call-queue.md) <br> |Le permite configurar cómo se administran las colas de llamadas para su organización: por ejemplo, configurar saludos y música en espera, buscar el siguiente agente de llamadas disponible para administrar la llamada, etc.  <br/> Tenga en cuenta *que los usuarios* deben tener habilitada la voz para recibir llamadas de una cola de llamadas.|
|[Música en espera](music-on-hold.md) | Reproduce música predeterminada definida por el servicio o música personalizada cargada por el administrador de inquilinos cuando se pone en espera una llamada externa de la red telefónica conmutada (RTC). Esta característica funciona para las llamadas de RTC a Teams de uno a uno, además de las llamadas realizadas en una cola de llamadas. Esta característica proporciona paridad de notificaciones en espera con otras plataformas. |
|Iniciar/responder llamadas (por nombre y número)   |Permite a los usuarios responder llamadas entrantes con un toque y realizar llamadas salientes marcando el número de teléfono completo o haciendo clic en un nombre en el cliente.   |
|[Opciones de desvío de llamadas y llamadas simultáneas](https://support.office.com/article/call-forwarding-call-groups-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)  |Permite a los usuarios configurar reglas de reenvío para que las llamadas puedan ir con ellas a cualquier lugar o que las llamadas se desvíen a compañeros o al correo de voz.   |
|[Recogida y desvío de llamadas grupales al grupo](call-sharing-and-group-call-pickup.md)  | Permite a los usuarios compartir las llamadas entrantes con sus compañeros para que estos puedan responder a las llamadas que se produzcan cuando el usuario no esté disponible. Menos perjudicial para los destinatarios que otras formas de uso compartido de llamadas (como desvío de llamadas o llamadas simultáneas) porque los usuarios pueden configurar cómo quieren recibir una notificación de una llamada compartida entrante. |
|[Transferir una llamada y una transferencia consultiva](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)  |Permite a los usuarios transferir llamadas a otra persona. O bien, si tienen que salir de la oficina pero quieren continuar con la conversación, pueden transferir las llamadas desde su teléfono IP o PC a su teléfono móvil.  <br/> Tenga en cuenta que *no* es necesario que los usuarios tengan habilitada la voz para recibir llamadas transferidas de otro usuario. |
|[Transferir al correo de voz en mitad de la llamada*](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)  | Permite que los usuarios se transfieran al correo de voz durante una llamada. |
|[Estacionar llamadas y recuperar](call-park-and-retrieve.md)   | Permite a los usuarios poner una llamada en espera en el servicio de Teams en la nube. Cuando se estaciona una llamada, el servicio genera un código único para la recuperación de la llamada. El usuario que estacionó la llamada u otra persona puede usar ese código y una aplicación o dispositivo compatible para recuperar la llamada.  |
|Llamar al número de teléfono desde la búsqueda   | Permite a los usuarios realizar una llamada desde el cuadro de búsqueda mediante el comando /call y especificando un nombre o un número.  |
|[Identificador de llamada](how-can-caller-id-be-used-in-your-organization.md)   |Las llamadas desde dentro de la empresa muestran un identificador de llamada detallado que extrae información del directorio corporativo y muestra la identificación de la imagen y el puesto en lugar de solo un número de teléfono. Para las llamadas de números de teléfono externos, se muestra el identificador de llamada proporcionado por el proveedor de servicios telefónicos. Si los números de teléfono externos son números secundarios en el directorio corporativo, se mostrará la información del directorio corporativo.   |
|Cambio de dispositivo   |Permite a los usuarios reproducir una llamada o reunión en otro dispositivo HID que esté conectado a Teams; por ejemplo, cambiar de los altavoces de su PC a unos auriculares.    |
|Enrutamiento de llamadas basado en presencia  |Controla las comunicaciones entrantes con presencia, lo que permite al usuario bloquear todas las comunicaciones entrantes excepto las indicadas específicamente.   |
|[Teclado de marcado integrado](https://support.office.com/article/use-the-dial-pad-in-teams-27bc60b5-74c0-4e9c-808b-da4db9514d89)  | Permite a los usuarios marcar por nombre o número en cualquier lugar de la barra de búsqueda y en el teclado de marcado, lo que acelera el proceso de realizar llamadas salientes.  |
|Llamadas federadas   |Permite a los usuarios conectarse, comunicarse y colaborar de forma segura con usuarios en inquilinos federados.   |
|[Realizar y recibir una videollamada](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)  | Si la cuenta del usuario está habilitada para videollamadas, el usuario puede realizar videollamadas cara a cara con sus contactos. Todo lo que necesitan es una cámara, los altavoces y el micrófono de su pc. Los usuarios también pueden usar auriculares si su equipo no tiene un dispositivo de audio integrado. |
|[Correo de voz en la nube](set-up-phone-system-voicemail.md)  | Cuando un usuario recibe un correo de voz, se entrega en su buzón de Exchange como un correo electrónico con el mensaje de correo de voz como datos adjuntos. Los usuarios pueden escuchar sus mensajes en su teléfono de escritorio certificado y en todas las aplicaciones de Teams o Skype Empresarial. La compatibilidad con la transcripción del correo de voz se agregó en marzo de 2017 y está habilitada de forma predeterminada para todas las organizaciones y usuarios. <br> Tenga en cuenta que los usuarios *no* necesitan una licencia de Sistema telefónico, *ni* deben tener habilitada la voz para usar Correo de voz en la nube características.    |
|[Correo de voz en la nube configuración de usuario](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US)  | Permite a los usuarios configurar la configuración del cliente para los saludos del correo de voz, las reglas de respuesta de llamadas y el idioma del saludo, incluidos los saludos de fuera de la oficina. <br> Tenga en cuenta que los usuarios *no* necesitan una licencia de Sistema telefónico, *ni* deben tener habilitada la voz para usar Correo de voz en la nube características.  |
|[Timbre secundario](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)  | Los usuarios con varios dispositivos de altavoz conectados a su PC pueden elegir configurar un dispositivo secundario para que suene además de su altavoz predeterminado. Por ejemplo, un usuario con unos auriculares conectados al equipo y altavoces de escritorio puede elegir que suenen tanto los auriculares como los altavoces de escritorio cuando se recibe una llamada para que no se pierda ninguna llamada.  |
|[Alertas de tono distintivo](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) (solo teams) |Permite a los usuarios elegir tonos independientes para las llamadas normales, las llamadas desviadas y las llamadas delegadas, para que puedan distinguir el tipo de llamada.   |
|[Apariencia de línea compartida](shared-line-appearance.md)  | Permite a los usuarios compartir su línea telefónica para que otro usuario pueda realizar y recibir llamadas en su nombre.|
|[Ocupado en ocupado](teams-calling-policy.md) (solo Teams)  | Una directiva de llamada que le permite configurar cómo se administran las llamadas entrantes cuando un usuario es: <ul><li>en una llamada </li><li>en una conferencia</li><li>tiene una llamada en espera. </li></ul> El autor de la llamada recibirá una de las siguientes respuestas: <ul><li>escuchar una señal de ocupado cuando el destinatario de la llamada está en el teléfono</li> <li>se redirigirán en consecuencia a la configuración no respondida del usuario. Una opción permite al autor de la llamada dejar un correo de voz para el usuario que ya está en una llamada.</li></ul> El destinatario de la llamada recibe una notificación de llamada perdida, pero no puede responder a las llamadas entrantes. Esta característica está deshabilitada de forma predeterminada, pero la puede activar el administrador de inquilinos.|
|[Bloqueo de llamadas](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US)  | Permite a los usuarios agregar números de teléfono (RTC) a una lista de bloqueados para que la siguiente llamada de ese número no suene al usuario.|
|[Teléfonos de área común](set-up-common-area-phones.md)  | Un teléfono de área común suele colocarse en un área como un vestíbulo o una sala de conferencias para que esté disponible para varias personas. Los teléfonos de área común se configuran como dispositivos en lugar de usuarios y pueden iniciar sesión automáticamente en una red.|
|[Compatibilidad con omisión de medios](direct-routing-plan-media-bypass.md) (solo para enrutamiento directo de Teams)  | Para mejorar el rendimiento, se conservan medios entre el controlador de borde de sesión (SBC) y el cliente en lugar de enviarlo a través del sistema telefónico. |
|[Enrutamiento de números no asignados](routing-calls-to-unassigned-numbers.md) | Permite el enrutamiento de números no asignados a usuarios, operadores automáticos, colas de llamadas o un anuncio personalizado. |

## <a name="availability-in-gcc-high-and-dod-clouds"></a>Disponibilidad en nubes GCC High y DoD
<a name="bkmk_setup"> </a>

Las siguientes capacidades aún no están disponibles en las nubes GCC High y DoD. 

- [Configuración de llamadas para el tono secundario, el correo de voz y la delegación mejorada](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)
- [Transferir al correo de voz en mitad de la llamada](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)
- Llamar al número de teléfono desde la barra de búsqueda
- Música en espera
- Búsqueda inversa de números en Azure AD

## <a name="related-topics"></a>Temas relacionados

- [¿Qué es el Sistema telefónico?](what-is-phone-system-in-office-365.md)
- [Voz en la nube de Microsoft Teams](cloud-voice-landing-page.md)
- [Configurar el Sistema telefónico](setting-up-your-phone-system.md)
- [¿Qué plan de llamada es adecuado para usted?](calling-plan-landing-page.md)
- [Supervisar y administrar la calidad de las llamadas](monitor-call-quality-qos.md)
- [Licencias complementarias de Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Precios de Sistema telefónico](https://products.office.com/microsoft-teams/voice-calling#requirements)
- [Teams para infraestructura de escritorio virtualizada con llamadas y reuniones](teams-for-vdi.md#teams-on-vdi-with-calling-and-meetings)
