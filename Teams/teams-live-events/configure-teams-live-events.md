---
title: Configuración de eventos en directo en Microsoft Teams
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: tonysmit
search.appverid: MET150
description: Obtenga información sobre cómo configurar las opciones de evento en directo en Microsoft Teams, incluida la configuración de visibilidad de attendee y las opciones de grabación.
appliesto:
- Microsoft Teams
ms.openlocfilehash: fcd9bc02257d67f1af959d2158042ea73545a25e
ms.sourcegitcommit: 6447a3aa060452c8d6879524cd6a56aecf33b152
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "25354359"
---
# <a name="configure-live-events-in-microsoft-teams"></a>Configuración de eventos en directo en Microsoft Teams
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

## <a name="set-up-event-support-link"></a>Configurar el vínculo de soporte técnico (evento)
Esto es el vínculo que se mostrará a los asistentes de evento en directo. 

En Windows PowerShell, ejecute lo siguiente:
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
## <a name="configure-attendee-visibility-options"></a>Configurar las opciones de visibilidad de attendee
Esto permite que los organizadores de evento live crear eventos con visibilidad de attendee adecuado.

|**Valores**  |**Comportamiento**  |
|---------|---------|
|Todos     |El usuario tiene una opción para crear eventos en directo con la visibilidad de attendee siguientes: Public, todos los usuarios de la compañía y personas específicas. |
|EveryoneInCompany     |El usuario tiene una opción para crear eventos en directo con la visibilidad de attendee siguientes: todas las personas de la compañía y personas específicas. El usuario no puede crear eventos en directo que pueden ser atendidos por los usuarios anónimos.|
|InvitedUsers |El usuario sólo puede crear eventos en directo que se limitan a personas específicas, tal como se especificó por el organizador del evento. El usuario no puede crear eventos en directo con público y todas las personas de la autenticación de la compañía. |

Use la opción BroadcastAttendeeVisibility en TeamsMeetingBroadcastPolicy en PowerShell para controlar si los usuarios pueden programar la difusión de presentaciones eventos que se pueden ver los asistentes anónimo. 

A menos que haya asignado una directiva personalizada a los usuarios, los usuarios obtendrán una directiva Global, que tiene un valor predeterminado establecido en EveryoneInCompany. 
 
En Windows PowerShell, ejecute lo siguiente para permitir a los usuarios crear eventos anónimos en la directiva global:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="configure-recording-options"></a>Configurar las opciones de grabación
> [!NOTE]
> Esta opción es aplicable a los eventos que usan solo el método de producción de inicio rápido.

Esto permite a los administradores para controlar si siempre se registran los eventos en directo, nunca se registró, o si el organizador del evento puede optar por registrar el evento o no.  

|**Valores**  |**Comportamiento**  |
|---------|---------|
|Siempre están habilitadas |Siempre se registran los eventos live organizados por este usuario. El usuario no tiene una opción para invalidar. Si se registra el evento en directo, los miembros del equipo de evento pueden descargar la grabación después del evento, y los asistentes pueden verla el evento después de que el evento es a través de. |
|AlwaysDisabled |Nunca se registran los eventos live organizados por este usuario. El usuario no tiene una opción para invalidar. Si se registra el evento en directo, no se crea ninguna grabación para los miembros del equipo (evento), y los asistentes no pueden inspeccionar el evento después de que se encuentra sobre. |
|UserOverride |Usuario puede decidir si se registra el evento en directo para que se puede crear un archivo de grabación para los miembros del equipo (evento), y los asistentes pueden verla el evento después de que el evento es a través de. |

Use la opción *BroadcastRecordingMode* en **TeamsMeetingBroadcastPolicy** en PowerShell para controlar las opciones de los eventos de live creados por el organizador del evento live de grabación.

En Windows PowerShell, ejecute el siguiente cmdlet para actualizar el modo de grabación en la directiva global:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="configure-real-time-transcription-and-translation-in-teams-live-events-coming-soon"></a>Configurar la transcripción en tiempo real y traducción en eventos en los equipos directo (próximamente)
> [!NOTE]
> Esta opción es aplicable a los eventos que usan solo el método de producción de inicio rápido.

Esto permite que los organizadores de evento en directo activar la traducción de los asistentes del evento en directo y títulos en tiempo real. 

Use la opción *AllowBroadcastTranscription* en **TeamsMeetingBroadcastPolicy** en PowerShell para controlar si los asistentes del evento en directo podrá vea transcripción y traducción. Encontrará más información acerca de cómo administrar **TeamsMeetingBroadcastPolicy** con Office 365 PowerShell aquí.  

A menos que haya asignado una directiva personalizada a los usuarios, los usuarios obtendrán una directiva Global, que tiene la transcripción y traducción deshabilitado de forma predeterminada.

En Windows PowerShell, ejecute el siguiente cmdlet para activar la transcripción y traducción en para los asistentes de eventos en la directiva global:
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```
## <a name="administrative-tools"></a>Herramientas administrativas 
Aunque Microsoft directamente controla todos los centros de datos en línea de Office 365 y es responsable de rendimiento general del sistema, puede controlar sólo una parte de los elementos que se combinan para proporcionar la experiencia de total para los usuarios de Office 365. Las organizaciones a sí mismos son responsables de las conexiones de red en los centros de datos, la red del cliente área extensa (WAN), y redes de área local del cliente (LAN). Además, están a cargo de los dispositivos de usuario y su configuración.También son responsables del mantenimiento de la licencia necesaria por usuario para cualquier característica que desee, incluidos, pero sin limitarse a, la capacidad para administrar estas características, para siempre y cuando el usuario necesita tener acceso a la característica.

Los clientes pueden usar las siguientes herramientas para administrar una variedad de tareas relacionadas de eventos en directo de los equipos.
- [Centro de administración de Microsoft Office 365](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_Office365admincenterl)
- [Microsoft Teams y Skype para el centro de administración de negocio en línea](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_ExchangeAdministrationCenter)
- [Centro de administración de Microsoft Stream](https://stream.microsoft.com)
- [Windows PowerShell remoto](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_RemoteWindowsPowerShell)

## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?
Cuando se trata de Windows PowerShell, que toda la información sobre administración de usuarios y qué usuarios pueden o no pueden para hacer. Con Windows PowerShell, puede administrar Office 365 y Skype para profesionales Online mediante un único punto de administración que puede simplificar su trabajo diario cuando haya varias tareas para hacer. Para empezar con Windows PowerShell, vea estos temas:
 - [Una introducción a Windows PowerShell y Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
 - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
 - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
 - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
 - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
