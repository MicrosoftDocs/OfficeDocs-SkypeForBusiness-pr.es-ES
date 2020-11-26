---
title: Administrar directivas de reunión
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.overview
- ms.teamsadmincenter.meetingpolicies.audioandvideo
- ms.teamsadmincenter.meetingpolicies.contentsharing
- ms.teamsadmincenter.meetingpolicies.general
- ms.teamsadmincenter.meetingpolicies.participantandguests
- seo-marvel-apr2020
description: Aprenda a administrar la configuración de la Directiva de reunión en Teams y Úsela para controlar las características disponibles para los participantes de la reunión para las reuniones programadas por los usuarios.
ms.openlocfilehash: 8d701f32cbaf133b03573394d48772b12488b8fe
ms.sourcegitcommit: eaab12a7a760f8a197632e1d28773728b5d1dcef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "49429401"
---
# <a name="manage-meeting-policies-in-teams"></a>Administrar directivas de reunión en Teams

::: zone target="docs"
Las Directivas de reunión se usan para controlar las características disponibles para sus participantes en reuniones programadas por usuarios de la organización. Puede usar la directiva global (predeterminada para toda la organización) que se crea automáticamente o crear y asignar directivas personalizadas. Las directivas de reunión se administran en el centro de administración de Microsoft Teams o mediante [PowerShell](teams-powershell-overview.md).

> [!NOTE]
> Para obtener información sobre el uso de roles para administrar los permisos de moderadores y asistentes de reuniones, vea [roles de una reunión de Teams](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).

Puede implementar directivas de las siguientes maneras, que afectan a la experiencia de la reunión para los usuarios antes de que se inicie una reunión, durante una reunión o después de una reunión.

|Tipo de implementación  |Descripción  |
|---------|---------|
|Por organizador    |Al implementar una directiva por organizador, todos los participantes de la reunión heredan la Directiva del organizador. Por ejemplo, **admitir automáticamente a personas** es una directiva para el organizador y controla si los usuarios se unen a la reunión directamente o espera en la sala de espera para las reuniones programadas por el usuario al que se le asigna la Directiva.          |
|Por usuario    |Al implementar una directiva por usuario, solo se aplica la Directiva por usuario para restringir determinadas características para el organizador o los participantes de la reunión. Por ejemplo, **permitir reunirse ahora en canales** es una directiva por usuario.     |
|Por organizador y por usuario     |Al implementar una combinación de una directiva por organizador y por usuario, ciertas características están restringidas para los participantes de la reunión en función de su Directiva y la Directiva del organizador. Por ejemplo, **permitir la grabación en la nube** es una directiva por organizador y por usuario. Active esta configuración para permitir que el organizador de la reunión y los participantes inicien y detengan una grabación.

Puede editar la configuración en la directiva global o crear y asignar una o más directivas personalizadas. Los usuarios recibirán la directiva global a menos que cree y asigne una directiva personalizada.

> [!NOTE]
> El botón detalles de la reunión estará disponible si un usuario tiene habilitadas las licencias de conferencia de audio o si el usuario permite conferencias de audio, de lo contrario, los detalles de la reunión no estarán disponibles.

## <a name="create-a-custom-meeting-policy"></a>Crear una directiva de reunión personalizada

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a directivas de reunión de **reuniones**  >  **Meeting policies**.
2. Seleccione **Agregar**.
3. Escriba un nombre y una descripción para la directiva. El nombre no puede contener caracteres especiales ni tener más de 64 caracteres.
4. Elija la configuración que desee.
5. Seleccione **Guardar**.

Por ejemplo, supongamos que tiene un grupo de usuarios y quiere limitar el ancho de banda que necesitaría la reunión. Cree una nueva directiva personalizada denominada "ancho de banda limitado" y deshabilite las opciones siguientes:

En **Audio y vídeo**:

- Desactive Permitir la grabación en la nube.
- Desactive Permitir vídeo IP.

En **Uso compartido de contenido**:

- Desactive el modo de uso compartido de la pantalla.
- Desactive Permitir pizarra.
- Desactive Permitir notas compartidas.

Luego asigne la directiva a los usuarios:

## <a name="edit-a-meeting-policy"></a>Editar una directiva de reunión

Puede editar la directiva global y las directivas personalizadas que cree.

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a directivas de reunión de **reuniones**  >  **Meeting policies**.
2. Seleccione la Directiva haciendo clic a la izquierda del nombre de la Directiva y, a continuación, seleccione **Editar**.
3. Desde aquí, realice los cambios que desee.
4. Seleccione **Guardar**.

> [!NOTE]
> A un usuario solo se le puede asignar una directiva de reunión a la vez.

## <a name="assign-a-meeting-policy-to-users"></a>Asignar una directiva de reunión a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> No puede eliminar una Directiva si los usuarios están asignados a ella. Primero debe asignar una directiva diferente a todos los usuarios afectados y, después, puede eliminar la directiva original.

## <a name="meeting-policy-settings"></a>Configuración de la Directiva de reunión

Cuando selecciona una directiva existente en la página **directivas** de la reunión o selecciona **Agregar** para agregar una nueva Directiva, puede establecer la configuración para lo siguiente.

- [General](#meeting-policy-settings---general)
- [Audio & vídeo](#meeting-policy-settings---audio--video)
- [Uso compartido de contenido](#meeting-policy-settings---content-sharing)
- [Participantes & invitados](#meeting-policy-settings---participants--guests)

::: zone-end

<a name="bkgeneral"> </a>

## <a name="meeting-policy-settings---general"></a>Configuración de la Directiva de reunión: General

- [Permitir reunirse ahora en los canales](#allow-meet-now-in-channels)
- [Permitir el complemento de Outlook](#allow-the-outlook-add-in)
- [Permitir programación de reuniones de canal](#allow-channel-meeting-scheduling)
- [Permitir la programación de reuniones privadas](#allow-scheduling-private-meetings)
- [Permitir reunirse ahora en reuniones privadas](#allow-meet-now-in-private-meetings)

### <a name="allow-meet-now-in-channels"></a>Permitir reunirse ahora en los canales

Permitir **reunirse ahora** es una directiva por usuario y se aplica antes de que se inicie una reunión. Esta configuración controla si un usuario puede iniciar una reunión no planeada en un canal de Teams. Si activa esta configuración, los usuarios podrán seleccionar el botón **reunirse** para iniciar una reunión no planeada o programar una reunión en el canal. El valor predeterminado es True.

![Captura de pantalla que muestra el icono reunirse ahora debajo de un mensaje](media/meeting-policies-meet-now.png) 

### <a name="allow-the-outlook-add-in"></a>Permitir el complemento de Outlook

Esta es una directiva por usuario y se aplica antes de que se inicie una reunión. Esta opción controla si las reuniones de Teams se pueden programar desde Outlook (Windows, Mac, Web y móvil).

![Captura de pantalla que muestra la posibilidad de programar una nueva reunión](media/meeting-policies-outlook-add-in.png)

Si desactiva esta opción, los usuarios no pueden programar. Reuniones de Teams al crear una nueva reunión en Outlook. Por ejemplo, en Outlook en Windows, la **nueva** opción de reunión de equipos no se mostrará en la cinta de opciones.

### <a name="allow-channel-meeting-scheduling"></a>Permitir programación de reuniones de canal

Use la Directiva de AllowChannelMeetingScheduling existente para controlar los tipos de eventos que se pueden crear en los calendarios de canal del equipo. Esta es una directiva por usuario y se aplica antes de que se inicie una reunión. Esta configuración controla si los usuarios pueden programar una reunión en un canal de Teams. Esta opción está activada de forma predeterminada.

Si esta directiva está desactivada, los usuarios no podrán crear nuevas reuniones de canal. Sin embargo, el organizador del evento puede editar las reuniones de canal existentes.

Programar una reunión se deshabilitará.

 ![Captura de pantalla que muestra la opción programar una reunión en Teams](media/schedule-meeting-option.png)

La selección de canal está deshabilitada.

![la opción calendario para seleccionar un canal en el que desee programar una reunión.](media/meeting-policies-select-a-channel-to-meet-in.png)

En la página publicaciones del canal, se deshabilitarán las siguientes características:

- Botón **programar una reunión** en el cuadro de redacción de respuesta del canal.
  ![botón programar una reunión responder cuadro de redacción](media/schedule-meeting-disabled-in-chat2.png)
  
- Botón **programar una reunión** en el encabezado del canal.
  ![botón programar una reunión en el encabezado del canal](media/schedule-now-in-header.png)

En el calendario del canal:

- El botón **Agregar nuevo evento** en el encabezado del calendario del canal se deshabilitará.
  ![botón en el encabezado de calendario del canal deshabilitado](media/add-new-event-disabled.png)

- Los usuarios no podrán arrastrar y seleccionar un bloque de tiempo en el calendario de canal para crear una reunión de canal.

- Los usuarios no pueden usar métodos abreviados de teclado para crear una reunión en el calendario del canal.

En el centro de administración:

La aplicación de calendario del canal se mostrará en la sección **aplicaciones de Microsoft** en la página directivas de permisos de aplicaciones.

 ![la Directiva permisos de aplicaciones en el centro de administración de Teams](media/manage-microsoft-apps-policy.png)

### <a name="allow-scheduling-private-meetings"></a>Permitir la programación de reuniones privadas

Esta es una directiva por usuario y se aplica antes de que se inicie una reunión. Esta opción controla si los usuarios pueden programar reuniones privadas en Teams. Una reunión es privada cuando no se publica en un canal de un equipo.

Tenga en cuenta que si desactiva permitir la programación de **reuniones privadas** y **permitir la programación de reuniones de canal**, los usuarios de Teams deshabilitarán las opciones **agregar asistentes requeridos** y agregar opciones de **canal** . Esta opción está activada de forma predeterminada.

### <a name="allow-meet-now-in-private-meetings"></a>Permitir reunirse ahora en reuniones privadas

Esta es una directiva por usuario y se aplica antes de que se inicie una reunión. Esta configuración controla si un usuario puede iniciar una reunión privada no planeada.  Esta opción está activada de forma predeterminada.

<a name="bkaudioandvideo"> </a>

## <a name="meeting-policy-settings---audio--video"></a>Configuración de la Directiva de reunión: vídeo & de audio

- [Permitir la transcripción](#allow-transcription)
- [Permitir la grabación en la nube](#allow-cloud-recording)
- [Modo para audio IP](#mode-for-ip-audio)
- [Modo para video IP](#mode-for-ip-video)
- [Permitir vídeo IP](#allow-ip-video)
- [Velocidad de bits multimedia (KB)](#media-bit-rate-kbs)

### <a name="allow-transcription"></a>Permitir la transcripción

Esta es una combinación de una directiva por organizador y por usuario. Esta configuración controla si se pueden usar las características de subtítulos y transcripción durante la reproducción de las grabaciones de la reunión. Si desactiva esta opción, las opciones de **Búsqueda** y **CC** no estarán disponibles durante la reproducción de la grabación de una reunión. La persona que ha iniciado la grabación necesita que esta opción esté activada para que la grabación también incluya transcripción.

Tenga en cuenta que la transcripción para las reuniones grabadas solo se admite en este momento para los usuarios que tienen el idioma de Teams establecido en inglés y cuando se habla de inglés en la reunión.

![las opciones de transcripción de una reunión](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a>Permitir la grabación en la nube

Esta es una combinación de una directiva por organizador y por usuario. Esta configuración controla si las reuniones de este usuario se pueden grabar. La grabación puede ser iniciada por el organizador de la reunión o por otro participante de la reunión si la configuración de directiva está activada para el participante y si es un usuario autenticado de la misma organización.

Las personas de fuera de su organización, como los usuarios federados y anónimos, no pueden iniciar la grabación. Los usuarios invitados no pueden iniciar ni detener la grabación.

![las opciones de grabación](media/meeting-policies-recording.png)

Echemos un vistazo al ejemplo siguiente.

|Usuario |Directiva de reuniones  |Permitir la grabación en la nube |
|---------|---------|---------|
|Daniela | Global   | Desactivado |
|Amanda | Location1MeetingPolicy | Activado|
|Juan (usuario externo) | No aplicable | No aplicable|

Las reuniones organizadas por Daniela no se pueden grabar y Amanda, que tiene la configuración de directiva habilitada, no puede grabar reuniones organizadas por Daniela. Las reuniones organizadas por Amanda se pueden grabar, pero Daniela, que tiene la configuración de directiva deshabilitada y Juan es un usuario externo, no puede grabar reuniones organizadas por Amanda.

Para obtener más información sobre la grabación de reuniones en la nube, vea [grabación de reuniones en la nube de Teams](cloud-recording.md).

### <a name="mode-for-ip-audio"></a>Modo para audio IP

Esta es una directiva por usuario. Esta opción controla si el audio puede activarse en las reuniones y en las llamadas grupales. Estos son los valores de esta configuración.

|Valor de configuración |Comportamiento  |
|---------|---------|
|**Audio entrante y saliente habilitado**    |El audio entrante y saliente está permitido en la reunión. Esta configuración es la predeterminada. |
|**Deshabilitado**     |El audio entrante y saliente está desactivado en la reunión.     |

Si se establece en **deshabilitado** para un usuario, ese usuario podrá programar y organizar reuniones, pero no podrá usar el audio. Para unirse a una reunión, deben llamar a través de la red de telefonía pública conmutada (RTC) o hacer la llamada de la reunión y unirse a ella por teléfono. Los participantes de la reunión que no tienen ninguna directiva asignada (por ejemplo, los participantes anónimos) tienen esta opción establecida en el **audio saliente y entrante habilitado** de forma predeterminada. En los clientes móviles de Teams, si esta configuración está deshabilitada, el usuario tiene que marcar la reunión a través de la RTC.

Esta configuración no se aplica a las llamadas de 1:1. Para restringir las llamadas de 1:1, configure una [Directiva](teams-calling-policy.md) de llamadas de equipo y desactive la opción **hacer llamadas privadas** . Esta configuración tampoco se aplica a dispositivos de salas de conferencias, como Surface Hub y los dispositivos de salas de Microsoft Teams.

Esta configuración aún no está disponible para los entornos Microsoft 365 administración pública Cloud (GCC), GCC High o Department of Defense (DoD).

Para obtener más información, consulte [administrar el audio y el vídeo de los participantes de la reunión](#manage-audiovideo-for-meeting-participants).

### <a name="mode-for-ip-video"></a>Modo para video IP

Esta es una directiva por usuario. Esta opción controla si se puede activar el vídeo en las reuniones y en las llamadas grupales. Estos son los valores de esta configuración.

|Valor de configuración |Comportamiento  |
|---------|---------|
|**Video entrante y saliente habilitado**    | El vídeo entrante y saliente está permitido en la reunión. Esta configuración es la predeterminada. |
|**Deshabilitado**     | El vídeo entrante y saliente está desactivado en la reunión. En los clientes móviles de Teams, los usuarios no pueden compartir vídeos ni fotos en la reunión. <br><br>Ten en cuenta que si el **modo para el audio IP** está deshabilitado, el **modo para el video IP** también quedará deshabilitado.  |

Si se establece en **deshabilitado** para un usuario, ese usuario no puede activar el vídeo o ver vídeos compartidos por otros participantes de la reunión. Los participantes de la reunión que no tienen ninguna directiva asignada (por ejemplo, los participantes anónimos) tienen este valor establecido en el **vídeo saliente y entrante habilitado** de forma predeterminada.

Esta configuración no se aplica a dispositivos de salas de conferencias, como Surface Hub y los dispositivos de salas de Microsoft Teams.

Esta configuración aún no está disponible para los entornos Microsoft 365 administración pública Cloud (GCC), GCC High o Department of Defense (DoD).

> [!NOTE]
> Tenga en cuenta que esta configuración controla tanto el vídeo entrante como el saliente, mientras que la configuración de **permitir el vídeo IP** controla el vídeo saliente. Para obtener más información, vea [¿cuál es la configuración de la Directiva de video IP?](#which-ip-video-policy-setting-takes-precedence) y [administrar el audio o vídeo de los participantes de la reunión](#manage-audiovideo-for-meeting-participants).

Para obtener más información, consulte [administrar el audio y el vídeo de los participantes de la reunión](#manage-audiovideo-for-meeting-participants).

### <a name="allow-ip-video"></a>Permitir vídeo IP

Esta es una combinación de una directiva por organizador y por usuario. El vídeo es un componente clave de las reuniones. En algunas organizaciones, los administradores pueden desear más control sobre las reuniones de los usuarios que tienen vídeo. Esta opción controla si se puede activar el vídeo en reuniones hospedadas por un usuario y en 1:1 y llamadas grupales iniciadas por un usuario. En los clientes móviles de Teams, esta opción controla si los usuarios pueden compartir fotos y vídeos en una reunión.

Reuniones organizadas por un usuario que tiene habilitada esta configuración de Directiva, permitir el uso compartido de vídeo en la reunión por parte de los participantes de la reunión, si los participantes también tienen la configuración de directiva habilitada. Los participantes de la reunión que no tienen ninguna directiva asignada (por ejemplo, participantes anónimos y federados) heredan la Directiva del organizador de la reunión.

> [!NOTE]
> Tenga en cuenta que esta configuración controla el vídeo saliente, mientras que el **modo de configuración de video IP** controla tanto el video entrante como el saliente. Para obtener más información, vea [¿cuál es la configuración de la Directiva de video IP?](#which-ip-video-policy-setting-takes-precedence) y [administrar el audio o vídeo de los participantes de la reunión](#manage-audiovideo-for-meeting-participants).

| Escritorio de Teams y cliente web |Cliente móvil de Teams  |
|:-------:|:-------:|
|![Captura de pantalla que muestra la combinación de reuniones con la configuración de audio y vídeo en el escritorio](media/meeting-policies-audio-video-settings.png)    |![Captura de pantalla que muestra la combinación de reuniones sreen con la configuración de audio/vídeo en dispositivos móviles](media/meeting-policies-mobile-join.png)          |

Echemos un vistazo al ejemplo siguiente.

|Usuario |Directiva de reuniones  |Permitir vídeo IP |
|---------|---------|---------|
|Daniela   | Global   | Activado       |
|Amanda    | Location1MeetingPolicy        | Desactivado      |

Las reuniones hospedadas por Daniela permiten que el vídeo esté activado. Daniela puede unirse a la reunión y encender el video. Amanda no puede activar el video en la reunión de Daniela porque la Directiva de Amanda está configurada para no permitir el vídeo. Amanda puede ver vídeos compartidos por otros participantes de la reunión.

En las reuniones hospedadas por Amanda, nadie puede activar el video, independientemente de la Directiva de vídeo que se les haya asignado. Esto significa que Daniela no puede activar el video en las reuniones de Amanda.  

Si Daniela llama Amanda con video on, Amanda puede contestar la llamada solo con audio.  Cuando la llamada está conectada, Amanda puede ver el vídeo de Daniela, pero no puede activar el vídeo. Si Amanda llama a Daniela, Daniela puede responder a la llamada con video y audio. Cuando la llamada está conectada, Daniela puede activar o desactivar el video, según sea necesario.

Para obtener más información, consulte [administrar el audio y el vídeo de los participantes de la reunión](#manage-audiovideo-for-meeting-participants).

#### <a name="which-ip-video-policy-setting-takes-precedence"></a>La configuración de directiva de video IP tiene prioridad

Para un usuario, tiene prioridad la configuración de directiva más restrictiva para el vídeo. A continuación se muestran algunos ejemplos.

|Permitir vídeo IP|Modo para video IP|Experiencia de reunión|
|---------|---------|---------|
|Organizador: **activado**<br><br>Participante: **activado** |Participante: **deshabilitado**        |El **modo de configuración de video IP** tiene prioridad. El participante que tiene asignada esta Directiva no puede activar o ver vídeos compartidos por otras personas.|
|Organizador: **activado**<br><br>Participante: **activado** |Participante: el **vídeo entrante y saliente está habilitado**          |El participante que tiene asignada esta Directiva puede activar o ver vídeos compartidos por otros usuarios.         |
|Organizador: **activado**<br><br>Participante: **deshabilitado** |Participante: el **vídeo entrante y saliente está habilitado**         |La configuración de **permitir video IP** tiene prioridad. Los participantes solo pueden ver el vídeo entrante y no pueden enviar video de salida.         |
|Organizador: **activado**<br><br>Participante: **deshabilitado** |Participante: **deshabilitado**         |El **modo de configuración de video IP** tiene prioridad. El participante no puede ver video entrante o saliente.|
|Organizador: **deshabilitado**    |       |La configuración de **permitir video IP** tiene prioridad porque está desactivada para el organizador. Nadie puede activar el video en las reuniones organizadas por el usuario que tenga asignada esta Directiva.         |

### <a name="manage-audiovideo-for-meeting-participants"></a>Administrar el audio y el vídeo de los participantes de la reunión

|Si desea...  |Establecer la siguiente configuración de Directiva  |
|---------|---------|
|Deshabilitar el audio y el vídeo de los participantes de las reuniones  |Modo para audio IP: **deshabilitado**<br> Modo para vídeo IP: **deshabilitado**<br>Permitir video IP: N/A       |
|Habilitar solo vídeo y audio entrante para los participantes en las reuniones  |Modo de audio IP: **habilitado el audio saliente y entrante**<br> Modo para video IP: **vídeo entrante y saliente habilitado**<br>Permitir video IP: **deshabilitado**       |
|Deshabilitar el vídeo para los participantes en las reuniones (los participantes solo tienen audio)|  Modo para audio IP: **Habilitar audio entrante y saliente**<br> Modo para vídeo IP: **deshabilitado**<br>Permitir video IP: N/A
|Habilitar el audio y el vídeo para los participantes en las reuniones    |Modo de audio IP: **habilitado el audio saliente y entrante** (predeterminado)<br> Modo para video IP: **vídeo entrante y saliente habilitado** (predeterminado)<br>Permitir video IP: **activado** (valor predeterminado)    |

Se aplica la directiva más restrictiva entre la Directiva del organizador de la reunión y la Directiva del usuario. Por ejemplo, si un organizador tiene una directiva que restringe el vídeo y la Directiva de un usuario no restringe el vídeo, los participantes de la reunión heredan la Directiva del organizador de la reunión y no tienen acceso al vídeo de las reuniones. Esto significa que pueden unirse a la reunión solo con audio.

> [!NOTE]
> Cuando un usuario inicia una llamada grupal para unirse por teléfono, no aparece la pantalla **usar teléfono para audio** . Este es un problema conocido que estamos trabajando para resolver. Para solucionar este problema, seleccione **audio del teléfono** en **otras opciones de combinación**.  

#### <a name="teams-mobile-clients"></a>Equipos clientes móviles

Para los usuarios de los clientes móviles de Teams, la capacidad de compartir fotos y vídeos durante una reunión también viene determinada por la opción **permitir** modo de vídeo IP o **IP** . En función de la configuración de directiva que tenga prioridad, la capacidad de compartir vídeos y fotos no estará disponible. Esto no afecta al uso compartido de la pantalla, que se configura con una configuración de [modo de uso compartido de pantalla](#screen-sharing-mode) independiente. Además, puede establecer una [Directiva de movilidad de equipos](https://docs.microsoft.com/powershell/module/skype/new-csteamsmobilitypolicy) para evitar que los usuarios móviles usen video IP a través de una conexión móvil, lo que significa que debe usar una conexión WiFi.

### <a name="media-bit-rate-kbs"></a>Velocidad de bits multimedia (KB)

Esta es una directiva por usuario. Esta configuración determina la velocidad de bits de multimedia para las transtransmisións de uso compartido de aplicaciones de audio, vídeo y vídeo en llamadas y reuniones para el usuario. Se aplica a los usuarios de la llamada o a la reunión, tanto al vínculo ascendente como al enlace descendente multimedia. Esta configuración le da un control granular sobre la administración del ancho de banda de su organización. En función de los escenarios de reuniones requeridos por los usuarios, le recomendamos disponer de suficiente ancho de banda para obtener una experiencia de buena calidad. El valor mínimo es 30 Kbps y el valor máximo depende del escenario de la reunión. Para obtener más información sobre el ancho de banda mínimo recomendado para reuniones, llamadas y eventos en vivo de buena calidad en Teams, consulte [requisitos de ancho de banda](prepare-network.md#bandwidth-requirements).

Si no hay suficiente ancho de banda para una reunión, los participantes verán un mensaje que indica una mala calidad de la red.

Para las reuniones que necesitan la experiencia de video de mayor calidad, como las reuniones de los paneles CEO y los equipos en vivo, le recomendamos que establezca el ancho de banda en 10 Mbps. Incluso cuando se establece la experiencia máxima, la pila de medios de Teams se adapta a condiciones de ancho de banda bajo cuando se detectan ciertas condiciones de red, según el escenario.

## <a name="meeting-policy-settings---content-sharing"></a>Configuración de la Directiva de reunión: uso compartido de contenido

- [Modo de uso compartido de pantalla](#screen-sharing-mode)
- [Permitir que un participante pueda ceder o solicitar el control](#allow-a-participant-to-give-or-request-control)
- [Permitir que un participante externo pueda ceder o solicitar el control](#allow-an-external-participant-to-give-or-request-control)
- [Permitir el uso compartido de PowerPoint](#allow-powerpoint-sharing)
- [Permitir pizarra](#allow-whiteboard)
- [Permitir notas compartidas](#allow-shared-notes)

### <a name="screen-sharing-mode"></a>Modo de uso compartido de pantalla

> [!Note]
> Esta característica aún está en desarrollo. La pantalla compartida es una directiva por participante.

Esta configuración controla si el uso compartido de ventanas o de escritorio está permitido en la reunión del usuario. Los participantes de la reunión que no tienen ninguna directiva asignada (por ejemplo, participantes anónimos, invitados, B2B y federados) heredan la Directiva del organizador de la reunión.

|Valor de configuración |Comportamiento  |
|---------|---------|
|**Pantalla completa**    | El uso compartido de escritorio completo y el uso compartido de aplicaciones están permitidos en la reunión |
|**Única aplicación**   | El uso compartido de aplicaciones está permitido en la reunión        |
|**Deshabilitado**     |La pantalla compartida y el uso compartido de aplicaciones se han desactivado en la reunión.       |

Echemos un vistazo al ejemplo siguiente.

|Usuario |Directiva de reuniones |Modo de uso compartido de pantalla |
|---------|---------|---------|
|Daniela  | Global   | Pantalla completa |
|Amanda   | Location1MeetingPolicy  | Deshabilitado |

Las reuniones hospedadas por Daniela permiten a los participantes de la reunión compartir la pantalla completa o una aplicación específica. Si Amanda se une a la reunión de Daniela, Amanda no puede compartir su pantalla o una aplicación específica porque su configuración de directiva está deshabilitada. En las reuniones hospedadas por Amanda, nadie puede compartir su pantalla o una sola aplicación, independientemente de la Directiva de modo de uso compartido de pantalla que se les haya asignado. Esto significa que Daniela no puede compartir su pantalla o una sola aplicación en las reuniones de Amanda.  

Por el momento, los usuarios no pueden reproducir video ni compartir su pantalla en una reunión de Teams si usan Google Chrome.

### <a name="allow-a-participant-to-give-or-request-control"></a>Permitir que un participante pueda ceder o solicitar el control

Esta es una directiva por usuario. Esta configuración controla si el usuario puede ceder el control del escritorio o de la ventana compartidos a otros participantes de la reunión. Para darle el control, mantenga el mouse sobre la parte superior de la pantalla.

Si esta configuración está activada para el usuario, la opción **ceder el control** se muestra en la barra superior de una sesión compartida.

![Captura de pantalla que muestra la opción ceder control](media/meeting-policies-give-control.png)

Si la configuración está desactivada para el usuario, la opción **ceder el control** no está disponible.

![Captura de pantalla que muestra que la opción ceder control no está disponible](media/meeting-policies-give-control-not-available.png)

Echemos un vistazo al ejemplo siguiente.

|Usuario |Directiva de reuniones  |Permitir al participante ceder o solicitar el control |
|---------|---------|---------|
|Daniela   | Global   | Activado       |
|Babek    | Location1MeetingPolicy        | Desactivado   |

Daniela puede ceder el control del escritorio o de la ventana compartidos a otros participantes de una reunión organizada por Babek mientras que Babek no puede ceder el control a otros participantes.

Para usar PowerShell para controlar quién puede ceder el control o aceptar solicitudes de control, use el cmdlet AllowParticipantGiveRequestControl.

> [!NOTE]
> Para conceder y tomar el control del contenido compartido durante el uso compartido, ambas partes deben usar el cliente de escritorio de Teams. El control no es compatible cuando cualquiera de las partes ejecuta Teams en un explorador. Esto se debe a una limitación técnica que planeamos solucionar.

### <a name="allow-an-external-participant-to-give-or-request-control"></a>Permitir que un participante externo pueda ceder o solicitar el control

Esta es una directiva por usuario. Si una organización tiene este valor para un usuario no controla lo que los participantes externos pueden hacer, independientemente de lo que haya establecido el organizador de la reunión. Este parámetro controla si los participantes externos pueden recibir control o solicitar el control de la pantalla del compartidor, en función de lo que el compartidor haya establecido dentro de las políticas de reuniones de su organización. Los participantes externos de las reuniones de Teams se pueden clasificar de la siguiente manera:  

- Usuario anónimo
- Usuarios invitados  
- Usuario B2B
- Usuario federado  

Si los usuarios federados pueden ceder el control a usuarios externos mientras lo comparten está controlado por la configuración de **permitir que un participante externo le dé o solicite** la configuración de control de su organización.

Para usar PowerShell para controlar si los participantes externos pueden ceder el control o aceptar solicitudes de control, use el cmdlet AllowExternalParticipantGiveRequestControl.

### <a name="allow-powerpoint-sharing"></a>Permitir el uso compartido de PowerPoint

Esta es una directiva por usuario. Esta configuración controla si el usuario puede compartir diapositivas de PowerPoint en una reunión. Los usuarios externos, incluidos los anónimos, los invitados y los usuarios federados, heredan la Directiva del organizador de la reunión.

Echemos un vistazo al ejemplo siguiente.

|Usuario |Directiva de reuniones  |Permitir el uso compartido de PowerPoint |
|---------|---------|---------|
|Daniela   | Global   | Activado       |
|Amanda   | Location1MeetingPolicy        | Desactivado   |

Amanda puede compartir diapositivas de PowerPoint en reuniones incluso si es el organizador de la reunión. Daniela puede compartir las diapositivas de PowerPoint incluso si la reunión está organizada por Amanda. Amanda puede ver los decks de diapositivas de PowerPoint compartidos por otros usuarios de la reunión, aunque no pueda compartir diapositivas de PowerPoint.

### <a name="allow-whiteboard"></a>Permitir pizarra

Esta es una directiva por usuario. Esta configuración controla si un usuario puede compartir la pizarra en una reunión. Los usuarios externos, incluidos los usuarios anónimos, B2B y federados, heredan la Directiva del organizador de la reunión.

Echemos un vistazo al ejemplo siguiente.

|Usuario |Directiva de reuniones  |Permitir pizarra|
|---------|---------|---------|
|Daniela   | Global   | Activado       |
|Amanda   | Location1MeetingPolicy        | Desactivado   |

Amanda puede compartir la pizarra en una reunión incluso si es el organizador de la reunión. Daniela puede compartir la pizarra incluso si una reunión está organizada por Amanda.  

### <a name="allow-shared-notes"></a>Permitir notas compartidas

Esta es una directiva por usuario. Esta configuración controla si un usuario puede crear y compartir notas en una reunión. Los usuarios externos, incluidos los usuarios anónimos, B2B y federados, heredan la Directiva del organizador de la reunión. Actualmente, la pestaña notas de la **reunión** solo se admite en reuniones con menos de 20 participantes.

Echemos un vistazo al ejemplo siguiente.

|Usuario |Directiva de reuniones  |Permitir notas compartidas |
|---------|---------|---------|
|Daniela   | Global   | Activado       |
|Amanda   | Location1MeetingPolicy | Desactivado |

Daniela puede tomar notas en las reuniones de Amanda y Amanda no puede tomar notas en ninguna reunión.

## <a name="meeting-policy-settings---participants--guests"></a>Configuración de la Directiva de reunión: participantes & invitados

Esta configuración controla los participantes de la reunión en la sala de espera antes de que se admitan en la reunión y el nivel de participación permitido en una reunión.

- [Permitir a personas anónimas iniciar una reunión](#let-anonymous-people-start-a-meeting)
- [Admitir automáticamente personas](#automatically-admit-people)
- [Permitir que los usuarios de acceso telefónico omitan la sala de recepción](#allow-dial-in-users-to-bypass-the-lobby)
- [Habilitar títulos en vivo](#enable-live-captions)
- [Permitir la conversación en reuniones](#allow-chat-in-meetings)

> [!NOTE]
>Las opciones para unirse a una reunión variarán en función de la configuración de cada grupo de equipos y del método de conexión. Si su grupo tiene audioconferencias y lo usa para conectarse, vea [audioconferencia](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365). Si su grupo de equipos no tiene audioconferencia, consulte [unirse a una reunión en Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).

### <a name="let-anonymous-people-start-a-meeting"></a>Permitir a personas anónimas iniciar una reunión

Esta es una directiva por organizador que permite reuniones de conferencia de acceso telefónico local no superpuestos. Esta opción controla si los usuarios de acceso telefónico local pueden unirse a la reunión sin un usuario autenticado de la organización en la asistencia. De forma predeterminada, esta opción está desactivada, lo que significa que los usuarios de acceso telefónico estarán en la sala de espera hasta que un usuario autenticado de la organización se una a la reunión.

> [!NOTE]
> Si esta opción está desactivada y un usuario de acceso telefónico se une a la reunión en primer lugar y se coloca en la sala de recepción, el usuario de la organización debe unirse a la reunión con un cliente de Teams para admitir al usuario de la sala de recepción. No hay ningún control de sala de recepción disponible para los usuarios marcados.

### <a name="automatically-admit-people"></a>Admitir automáticamente personas

Esta es una directiva por organizador. Esta opción controla si los usuarios pueden unirse a una reunión directamente o aguardar en la sala de espera hasta que un usuario autenticado las admita. Esta configuración no se aplica a los usuarios de acceso telefónico.

![Captura de pantalla que muestra una reunión con un usuario en la sala de recepción](media/meeting-policies-lobby.png)

 Los organizadores de reuniones pueden hacer clic en **Opciones de reunión** en la invitación a la reunión para cambiar esta configuración para cada reunión que programe.

> [!NOTE]
> En las opciones de la reunión, la configuración se denomina "quién puede omitir la sala de recepción". Si cambia la configuración predeterminada para cualquier usuario, se aplicará a todas las reuniones nuevas organizadas por ese usuario y a las reuniones anteriores en las que el usuario no haya modificado las opciones de la reunión.
  
|Valor de configuración  |Comportamiento de combinación |
|---------|---------|
|**Todos**   |Todos los participantes de la reunión se unen directamente desde la sala de espera. Esto incluye usuarios autenticados, usuarios externos de organizaciones de confianza (federados), invitados y usuarios anónimos.     |
|**Todas las personas de la organización y las organizaciones federadas**     |Usuarios autenticados dentro de la organización, incluidos los usuarios invitados y los usuarios de organizaciones de confianza, únase a la reunión directamente sin tener que esperar en la sala de espera.  Los usuarios anónimos esperan en la sala de espera.   |
|**Todas las personas de su organización**    |Los usuarios autenticados de la organización, incluidos los invitados, se unen a la reunión directamente, sin tener que esperar en la sala de espera.  Los usuarios de organizaciones de confianza y usuarios anónimos esperan en la sala de espera. Esta configuración es la predeterminada.           |
|**Solo Organizer**    |Solo los organizadores de reuniones pueden unirse a la reunión directamente, sin tener que esperar en la sala de espera. Todos los demás, incluidos los usuarios autenticados de la organización, los usuarios invitados, los usuarios de organizaciones de confianza y los usuarios anónimos deben esperar en la sala de espera.           |

### <a name="allow-dial-in-users-to-bypass-the-lobby"></a>Permitir que los usuarios de acceso telefónico omitan la sala de recepción

Esta es una directiva por organizador. Esta opción controla si las personas que marcan por teléfono se unen a la reunión directamente o esperan en la sala independientemente de la configuración **admitir automáticamente** a los usuarios. Esta opción está desactivada de forma predeterminada. Cuando esta opción está desactivada, los usuarios de acceso telefónico local esperarán en la sala de espera hasta que un usuario de la organización se una a la reunión con un cliente de Teams y lo retenga. Cuando esta configuración está activada, los usuarios de acceso telefónico local se unirán automáticamente a la reunión cuando un usuario de la organización se una a la reunión.

> [!NOTE]
> Si un usuario de acceso telefónico se une a una reunión antes de que un usuario de la organización se una a la reunión, se colocará en la sala de espera hasta que un usuario de la organización se una a la reunión con un cliente de Teams y se pueda tener acceso a ella. Si cambia la configuración predeterminada para cualquier usuario, se aplicará a todas las reuniones nuevas organizadas por ese usuario y a las reuniones anteriores en las que el usuario no haya modificado las opciones de la reunión.

### <a name="enable-live-captions"></a>Habilitar títulos en vivo

Esta es una directiva por usuario y se aplica durante una reunión. Esta configuración controla si la opción **Activar títulos en vivo** está disponible para que el usuario Active y desactive los subtítulos en vivo en las reuniones que asiste el usuario.  

![Captura de pantalla que muestra la opción Activar subtítulos en vivo](media/meeting-policies-live-captions.png)

|Valor de configuración |Comportamiento  |
|---------|---------|
|**Desactivado pero el usuario puede invalidar**     | Los subtítulos dinámicos no se activan automáticamente para el usuario durante una reunión. El usuario ve la opción **Activar títulos en vivo** en el menú de desbordamiento (**...**) para activarlo. Esta configuración es la predeterminada. |
|**Deshabilitado**     | Los subtítulos en vivo se deshabilitan para el usuario durante la reunión. El usuario no tiene la opción de activarlos.          |

<a name="bkcontentsharing"> </a>

### <a name="allow-chat-in-meetings"></a>Permitir la conversación en reuniones

Esta es una configuración por participante. Esta opción controla si se permite la conversación de la reunión en la reunión del usuario.

<a name="bkparticipantsandguests"> </a>

## <a name="meeting-policy-settings---designated-presenter-role-mode"></a>Configuración de la Directiva de reunión: modo de rol de moderador designado

Esta es una directiva por usuario. Esta opción le permite cambiar el valor predeterminado de la opción **¿quién puede presentar?** en **Opciones de reunión** en el cliente de Teams. Esta configuración de directiva afecta a todas las reuniones, incluidas las reuniones reunirse ahora.

La **configuración** permite a los organizadores de reuniones elegir quién puede ser moderador de una reunión. Para obtener más información, consulte [cambiar la configuración de participantes para una reunión de Teams](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) y [roles en una reunión de Teams](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).

Actualmente, solo puede usar PowerShell para establecer esta configuración de directiva. Puede editar una directiva de reunión existente de Teams mediante el cmdlet [set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) . O bien, cree una nueva Directiva de reunión de Teams mediante el cmdlet [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) y asígnela a los usuarios.

Para especificar el valor predeterminado de la configuración ¿ **quién puede presentar?** en Teams, establezca el parámetro **DesignatedPresenterRoleMode** en una de las siguientes opciones:

- **EveryoneUserOverride**: todos los participantes de la reunión pueden ser moderadores. Este es el valor predeterminado. Este parámetro corresponde a la configuración **todos** en Teams.
- **EveryoneInCompanyUserOverride**: los usuarios autenticados de la organización, incluidos los invitados, pueden ser moderadores. Este parámetro corresponde a la configuración de las **personas de mi organización** de Teams.
- **OrganizerOnlyUserOverride**: solo el organizador de la reunión puede ser Moderador y todos los participantes de la reunión se designan como asistentes. Este parámetro corresponde a la configuración **solo yo** de Teams.

Tenga en cuenta que después de establecer el valor predeterminado, los organizadores de reuniones pueden cambiar esta configuración en Teams y elegir quién puede presentar en las reuniones que programan.

## <a name="meeting-policy-settings---meeting-attendance-report"></a>Configuración de la Directiva de reunión-informe de asistencia a reuniones

Esta es una directiva por usuario. Esta configuración controla si los organizadores de reuniones pueden descargar el [Informe de asistencia](teams-analytics-and-reports/meeting-attendance-report.md)a la reunión.

Actualmente, solo puede usar PowerShell para establecer esta configuración de directiva. Puede editar una directiva de reunión existente de Teams mediante el cmdlet [set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) . O bien, cree una nueva Directiva de reunión de Teams mediante el cmdlet [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) y asígnela a los usuarios.

Para habilitar el organizador de la reunión para que descargue el informe de asistencia a reuniones, establezca el parámetro **AllowEngagementReport** en **habilitado**. Cuando se habilita, la opción para descargar el informe se muestra en el panel **participantes** .

Para evitar que un organizador de la reunión Descargue el informe, establezca el parámetro en **deshabilitado**. Esta opción está deshabilitada de forma predeterminada y la opción para descargar el informe no está disponible.

## <a name="meeting-policy-settings---meeting-provider-for-islands-mode"></a>Configuración de la Directiva de reunión-proveedor de la reunión para el modo islas

Esta es una directiva por usuario. Esta opción controla qué complemento de la reunión de Outlook se usa para *los usuarios que están en modo islas*. Puede especificar si los usuarios solo pueden usar el complemento de reuniones de equipos o bien la reunión de Teams y los complementos de reuniones de Skype empresarial para programar reuniones en Outlook.

Solo puede aplicar esta directiva a usuarios que están en modo islas y tener el parámetro **AllowOutlookAddIn** establecido en **true** en la Directiva de reuniones de Teams.

Actualmente, solo puede usar PowerShell para establecer esta Directiva. Puede editar una directiva de reunión existente de Teams mediante el cmdlet [set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) . O bien, cree una nueva Directiva de reunión de Teams mediante el cmdlet [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) y asígnela a los usuarios.

Para especificar qué complemento de la reunión quiere que esté disponible para los usuarios, establezca el parámetro **PreferredMeetingProviderForIslandsMode** de la siguiente manera:

- Establezca el parámetro en **TeamsAndSfB** para habilitar tanto el complemento de reuniones de equipos como el complemento de Skype empresarial en Outlook. Este es el valor predeterminado.
- Establezca el parámetro en **Teams** para habilitar solo el complemento de reunión de Teams en Outlook. Esta configuración de Directiva garantiza que todas las reuniones futuras tengan un vínculo para unirse a una reunión de equipos. No migra los vínculos de unirse a reuniones de Skype empresarial existentes a teams. Esta configuración de Directiva no afecta a la presencia, la conversación, las llamadas RTC o a cualquier otra funcionalidad de Skype empresarial, lo que significa que los usuarios continuarán usando Skype empresarial para estas capacidades.

  Si establece el parámetro en **Teams** y, a continuación, vuelve a **TeamsAndSfB**, los complementos de reuniones estarán habilitados. Sin embargo, ten en cuenta que los equipos existentes de los vínculos de unirse a la reunión no se migrarán a Skype empresarial. Solo las reuniones de Skype empresarial programadas después del cambio tendrán un vínculo para unirse a una reunión de Skype empresarial.

## <a name="meeting-policy-settings---video-filters-mode"></a>Configuración de la Directiva de reunión-modo filtros de vídeo

Esta es una directiva por usuario. Esta configuración controla si los usuarios pueden personalizar su fondo de vídeo en una reunión.

Actualmente, solo puede usar PowerShell para establecer esta Directiva. Puede editar una directiva de reunión existente de Teams mediante el cmdlet [set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) . O bien, cree una nueva Directiva de reunión de Teams mediante el cmdlet [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) y, a continuación, asigne la Directiva a los usuarios.

Para especificar si los usuarios pueden personalizar su fondo de vídeo en una reunión, establezca el parámetro **VideoFiltersMode** de la siguiente manera:

|Establecer valor en PowerShell |Comportamiento  |
|---------|---------|
|**Nofilters**     |El usuario no puede personalizar su fondo de vídeo.|
|**BlurOnly**     |El usuario tiene la opción de desenfocar el fondo de vídeo. |
|**BlurandDefaultBackgrounds**     |El usuario tiene la opción de desenfocar el fondo del vídeo o elegir un conjunto de imágenes predeterminado para usarlo como fondo. |
|**AllFilters**     |El uso tiene la opción de desenfocar el fondo del vídeo, elegir un conjunto de imágenes predeterminado o cargar imágenes personalizadas para usarlas como fondo. |

> [!NOTE]
> Teams no filtra las imágenes cargadas por los usuarios. Al usar la configuración **AllFilters** , debe tener directivas de organización interna para evitar que los usuarios carguen imágenes ofensivas o inadecuadas, o imágenes su organización no tiene derechos para usar con fondos de reuniones de Teams.

## <a name="related-topics"></a>Temas relacionados

- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
- [Asignar directivas a los usuarios de Teams](assign-policies.md)
- [Quitar la política de reunión de RestrictedAnonymousAccess Teams de los usuarios](meeting-policies-restricted-anonymous-access.md)
