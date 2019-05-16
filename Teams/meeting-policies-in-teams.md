---
title: Administrar directivas de reunión
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.date: 05/14/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
f1keywords:
- ms.teamsadmincenter.meetingpolicies.overview
- ms.teamsadmincenter.meetingpolicies.audioandvideo
- ms.teamsadmincenter.meetingpolicies.contentsharing
- ms.teamsadmincenter.meetingpolicies.general
- ms.teamsadmincenter.meetingpolicies.participantandguests
description: Obtenga información sobre cómo administrar la configuración de directivas en los equipos de la reunión.
ms.openlocfilehash: 99458e71ae02eb6307b3f363dbf7e060e1b4ed5b
ms.sourcegitcommit: 85b135cf622c9e9eb1857ef953bc618dc2cdb51e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "34036632"
---
# <a name="manage-meeting-policies-in-teams"></a>Administrar las directivas de reunión en los equipos

::: zone target="docs"
Las directivas de reunión se usan para controlar las características que están disponibles para los participantes de las reuniones programadas por los usuarios de la organización de la reunión. Después de crear una directiva y realice los cambios, a continuación, puede asignar a usuarios a la directiva. Administrar directivas de reunión en el centro de administración de Microsoft Teams o mediante el [uso de PowerShell](teams-powershell-overview.md).

Se pueden implementar directivas de las maneras siguientes, que afectan a la experiencia de reunión para los usuarios antes de una reunión se inicia, durante una reunión o después de una reunión. 

|Tipo de implementación  |Descripción  |
|---------|---------|
|Por organizador    |Cuando se implementa una directiva por organizador, todos los participantes de la reunión heredan la directiva del organizador. Por ejemplo, la **automáticamente admitir a personas** es una directiva por organizador y controles si los usuarios unirse a la reunión directamente o esperan en la sala de espera para las reuniones programadas por el usuario que se asigna la directiva.          |
|Por usuario    |Cuando se implementa una directiva por usuario, se aplica sólo la directiva por usuario para restringir determinadas características de los participantes en el organizador o reunión. Por ejemplo, **Permitir Reunirse ahora** es una directiva por usuario.     |
|Por usuario y por organizador     |Cuando se implementa una combinación de una directiva por usuario y por el organizador, algunas características están restringidos para los participantes en función de sus directivas y la directiva del organizador de la reunión. Por ejemplo, la **grabación de permitir en la nube** es una directiva por usuario y por el organizador. Activar esta opción para permitir que el organizador de la reunión y los participantes para iniciar y detener una grabación. 

De forma predeterminada, se crea una directiva con nombre Global (valor predeterminado de toda la organización). Todos los usuarios de su organización se asignará esta directiva de reunión de forma predeterminada. Puede realizar cambios en esta directiva o crear una o varias directivas personalizadas y asignar a usuarios a ellos. Cuando se crea una directiva personalizada, puede permitir o impedir que determinadas características que están disponibles para los usuarios y, a continuación, asignarla a uno o varios usuarios que tendrán las opciones que se aplican a ellos. 

## <a name="change-or-create-a-meeting-policy"></a>Cambiar o crear una directiva de reunión

Para cambiar o crear una directiva de reunión, vaya a la > de centro de administración de Microsoft Teams **reuniones** > **las directivas de reunión**. Seleccione una directiva de la lista o seleccione **nueva directiva**. Si está creando una nueva directiva, agregue un nombre y una descripción. El nombre no puede contener caracteres especiales ni tener más de 64 caracteres. Elija la configuración y, a continuación, seleccione **Guardar**.

Por ejemplo, supongamos que tiene un montón de usuarios y desea limitar la cantidad de ancho de banda que requieran sus reuniones. Debe crear una nueva directiva personalizada denominada "Ancho de banda limitado" y deshabilite a las siguientes opciones:

En **Audio & vídeo**:
- Desactivar la nube grabación
- Desactivar la opción permitir IP vídeo

En el **uso compartido de contenido**:
- Deshabilitar el modo de uso compartido de pantalla
- Desactivar la Pizarra
- Desactivar notas compartidas

A continuación, asigne la directiva a los usuarios.

> [!NOTE] 
> Un usuario puede asignar la directiva de reunión sólo una a la vez. 

## <a name="assign-a-meeting-policy-to-users"></a>Asignar una directiva de reunión a los usuarios

Si va a aplicar la directiva a un usuario, seleccione **los usuarios** en el panel de navegación izquierdo y, a continuación, haga clic en nombre para mostrar del usuario. En la página del usuario, junto a **las directivas asignadas**, seleccione **Editar**. A continuación, en el panel **Editar las directivas de usuario** , en **la directiva de reunión**, en la lista desplegable, seleccione la directiva de reunión y, a continuación, seleccione **Guardar**. También puede asignar directivas desde la lista de usuarios. Para ello, seleccione el usuario al hacer clic en a la izquierda del nombre para mostrar del usuario. Seleccione **Editar la configuración**. A continuación, en el panel **Editar configuración** , en **Directiva de reunión**, seleccione la directiva de la lista desplegable y, a continuación, seleccione **Guardar**. 
 
Si va a aplicar una directiva a más de un usuario, seleccione **los usuarios** en el panel de navegación izquierdo y, a continuación, seleccione cada usuario haciendo clic en a la izquierda del nombre de usuario y, a continuación, haga clic en **Editar configuración**. En el panel **Editar configuración** , en **Directiva de reunión**, seleccione la directiva de la lista desplegable y, a continuación, seleccione **Guardar**.
 
También puede asignar una directiva de reunión a uno o varios usuarios como sigue:

1. Vaya al **Centro de administración de equipos de Microsoft** > **reuniones** > **las directivas de reunión**.
2. Seleccione la directiva, haga clic en a la izquierda del nombre de la directiva.
3. Seleccione **Administrar usuarios**.
4. En el panel **Administrar usuarios** , buscar el usuario por nombre para mostrar o por su nombre de usuario, seleccione el nombre y, a continuación, seleccione **Agregar**. Repita este paso para cada usuario que desee agregar.
5. Cuando haya terminado de agregar usuarios, seleccione **Guardar**.
 
> [!NOTE] 
> No se puede eliminar una directiva si los usuarios se asignan a él. En primer lugar debe asignar una directiva diferente a todos los usuarios afectados y, a continuación, puede eliminar la directiva original.
 
## <a name="meeting-policy-settings"></a>Configuración de la directiva de reunión

Cuando seleccione una directiva existente en la página de **directivas de reunión** o seleccione **nueva directiva** para agregar una nueva directiva, puede configurar para la siguiente.

- [General](#meeting-policy-settings---general)
- [Audio & de vídeo](#meeting-policy-settings---audio--video)
- [Uso compartido de contenido](#meeting-policy-settings---content-sharing)
- [Invitados de & de los participantes](#meeting-policy-settings---participants--guests)

::: zone-end 

<a name="bkgeneral"> </a>

## <a name="meeting-policy-settings---general"></a>Configuración de la directiva de reunión - General

- [Permitir que Reunirse ahora de canales](#allow-meet-now-in-channels)
- [Permitir privada Reunirse ahora (próximamente)](#allow-private-meet-now-coming-soon)
- [Permitir que el complemento de Outlook](#allow-the-outlook-add-in)
- [Permitir la programación de reuniones de canal](#allow-channel-meeting-scheduling)
- [Permitir la programación de reuniones privadas](#allow-scheduling-private-meetings)

### <a name="allow-meet-now-in-channels"></a>Permitir que Reunirse ahora de canales

Se trata de una directiva por usuario y se aplica antes de una reunión se inicia. Esta configuración controla si un usuario puede iniciar una reunión ad hoc en un canal de los equipos. Si activa esta, cuando un usuario envía un mensaje en un canal de los equipos, el usuario puede haga clic en **Reunirse ahora** debajo del cuadro de redacción para iniciar una reunión ad hoc en el canal.

![reunión-directivas-reunirse-now.png](media/meeting-policies-meet-now.png)

### <a name="allow-private-meet-now-coming-soon"></a>Permitir privada Reunirse ahora (próximamente)

Se trata de una directiva por usuario y se aplica antes de una reunión se inicia. Esta configuración controla si un usuario puede iniciar una reunión ad hoc privada.  

### <a name="allow-the-outlook-add-in"></a>Permitir que el complemento de Outlook

Se trata de una directiva por usuario y se aplica antes de una reunión se inicia. Esta configuración controla si se pueden programar reuniones de los equipos desde dentro de Outlook (Windows, Mac, web y móviles).

![reunión-directivas-outlook-agregar-in.png](media/meeting-policies-outlook-add-in.png)

Si desactiva esta opción, los usuarios son no se puede programar reuniones de los equipos cuando se crea una nueva reunión en Outlook. Por ejemplo, en Outlook en Windows, la opción de **Nueva reunión de los equipos** no aparecerá en la cinta de opciones.

### <a name="allow-channel-meeting-scheduling"></a>Permitir la programación de reuniones de canal

Se trata de una directiva por usuario y se aplica antes de una reunión se inicia. Esta configuración controla si los usuarios pueden programar una reunión en un canal de los equipos.  Si desactiva esta opción, la opción de **programar una reunión** no estará disponible para el usuario al iniciar una reunión en un canal de los equipos y la opción de **Seleccionar un canal a satisfacer** no estará disponible para el usuario al programar una reunión de reuniones en los equipos.

![reunión de programación de las directivas de un meeting.png](media/meeting-policies-schedule-a-meeting.png)

![Meeting-Policies-Select-a-Channel-to-meet-in.png](media/meeting-policies-select-a-channel-to-meet-in.png)

### <a name="allow-scheduling-private-meetings"></a>Permitir la programación de reuniones privadas

Se trata de una directiva por usuario y se aplica antes de una reunión se inicia. Esta configuración controla si los usuarios pueden programar reuniones privadas en los equipos. Una reunión es privada cuando no se publica en un canal en un equipo.

Tenga en cuenta si desactiva **permitir programar reuniones privadas** y **programación de reuniones de canal de permitir**, la opción de **programar una reunión** no estará disponible y los usuarios podrán programar reuniones en los equipos.

<a name="bkaudioandvideo"> </a>

## <a name="meeting-policy-settings---audio--video"></a>Configuración de la directiva de reunión - & de Audio vídeo

- [Permitir la transcripción](#allow-transcription)
- [Permitir en la nube grabación](#allow-cloud-recording)
- [Permitir vídeo IP](#allow-ip-video)
- [Velocidad de bits Media (KB)](#media-bit-rate-kbs)
- [Habilitar live títulos (próximamente)](#enable-live-captions-coming-soon)

### <a name="allow-transcription"></a>Permitir la transcripción

Esto es una combinación de una directiva por usuario y por el organizador. Esta configuración controla si los títulos y las características de transcripción están disponibles durante la reproducción de grabaciones de la reunión. Si desactiva esta opción, las opciones de **búsqueda** y **CC** no estarán disponibles durante la reproducción de una grabación de la reunión. La persona que inició la grabación necesita esta opción activada de modo que la grabación también incluye transcripción. 

Tenga en cuenta que transcripción para reuniones grabadas está actualmente sólo admite para los usuarios que tienen el idioma en los equipos que se establece en inglés y cuando se habla inglés en la reunión.

![reunión-directivas-transcription.png](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a>Permitir en la nube grabación

Esto es una combinación de una directiva por usuario y por el organizador. Esta configuración controla si se pueden grabar las reuniones de este usuario. La grabación se puede iniciar por el organizador de la reunión o por otro participante de la reunión si la configuración de directiva está activada para el participante y el caso de un usuario autenticado de la misma organización.

Las personas de fuera de la organización, como los usuarios federados y anónimos, no pueden iniciar la grabación. Los usuarios invitados no se pueden iniciar o detener la grabación. 

![reunión-directivas-recording.png](media/meeting-policies-recording.png)

Veamos el ejemplo siguiente.

|Usuario |Directiva de reunión  |Permitir en la nube grabación |
|---------|---------|---------|
|Daniela | Global   | False |
|Amanda | Location1MeetingPolicy | True|
|John (usuarios externos) | No aplicable | No aplicable|

No se puede grabar las reuniones organizadas por Daniela y Amanda, que tenga habilitada la opción de directiva, no puede grabar las reuniones organizadas por Daniela. Se pueden grabar las reuniones organizadas por Amanda, sin embargo, Daniela, que tiene la configuración de directiva deshabilitada y John quién es un usuario externo, no se puede grabar las reuniones organizadas por Amanda.

Para obtener más información acerca de la grabación de la reunión en la nube, vea [los equipos en la nube de grabación de la reunión](cloud-recording.md).

### <a name="allow-ip-video"></a>Permitir vídeo IP

Esto es una combinación de una directiva por usuario y por el organizador. Vídeo es un componente clave a las reuniones. En algunas organizaciones, los administradores puede resultar útil mayor control sobre las reuniones que los usuarios tienen vídeo. Esta configuración controla si vídeo puede activarse en reuniones hospedadas por un usuario y en 1:1 las llamadas y llamadas de grupo iniciadas por un usuario. Las reuniones organizadas por un usuario que tenga esta directiva habilitada, permitir el uso compartido de vídeo de la reunión por los participantes de la reunión, si los participantes de la reunión también tienen la directiva habilitada. Participantes de la reunión que no tienen las directivas asignadas (por ejemplo, los participantes anónimos y federados) heredan la directiva de organizador de la reunión.

![reunión de directivas de audio vídeo settings.png](media/meeting-policies-audio-video-settings.png)

Veamos el ejemplo siguiente.

|Usuario |Directiva de reunión  |Permitir vídeo IP |
|---------|---------|---------|
|Daniela   | Global   | True        |
|Amanda    | Location1MeetingPolicy        | False      |

Reuniones hospedadas por Daniela permiten vídeos esté activada. Daniela puede unirse a la reunión y activar de vídeo. No se puede activar Amanda vídeo en Daniela de reunión debido a que la directiva de Amanda está establecida en no permitir vídeo. Amanda puede ver vídeos compartidos por otros participantes de la reunión.

En las reuniones hospedadas por Amanda, nadie puede activar vídeo, independientemente de la directiva de vídeo asignada a ellos. Esto significa que no se puede activar Daniela de vídeo en las reuniones de Amanda.  

Si Daniela llama a Amanda con vídeo en, Amanda puede responder a la llamada sólo con el audio.  Cuando la llamada está conectada, puede ver el vídeo de Daniela Amanda, pero no se puede activar de vídeo. Si llama a Amanda Daniela, Daniela puede responder a la llamada con audio y vídeo. Cuando está conectada a la llamada, Daniela puede activar o desactivar su vídeo, según sea necesario.

### <a name="media-bit-rate-kbs"></a>Velocidad de bits Media (KB)

Se trata de una directiva por organizador. Esta configuración determina la velocidad de bits de medios de audio, vídeo y vídeo-based aplicación uso compartido de las transmisiones de llamadas y reuniones para el usuario. Se aplica a la ascendentes y descendentes cruce seguro de medios para los usuarios de la llamada o reunión. Esta configuración proporciona un control granular sobre administración de ancho de banda en la organización. Dependiendo de los escenarios de reuniones requeridos por los usuarios, se recomienda disponer de suficiente ancho de banda de una experiencia de buena calidad. El valor mínimo es 30 Kbps y el valor máximo depende de la situación de la reunión. Para obtener más información acerca de los mínimos recomendados para las reuniones de buena calidad, las llamadas y eventos en directo en los equipos de ancho de banda, vea [requisitos de ancho de banda](prepare-network.md#bandwidth-requirements).

Si no hay suficiente ancho de banda para una reunión, los participantes verán un mensaje que indica la red con calidad deficiente.

Para las reuniones que necesitan la experiencia de vídeo más alta calidad, como consejero Delegado board reuniones y eventos en directo los equipos, se recomienda establecer el ancho de banda a 10 Mbps. Incluso cuando se establece la experiencia de máxima, la pila de medios de los equipos se adapta a las condiciones de ancho de banda bajo cuando se detectan determinadas condiciones de red, en función del escenario. 

### <a name="enable-live-captions-coming-soon"></a>Habilitar live títulos (próximamente)

Esto es una directiva por usuario y se aplica durante una reunión. Si esta opción está activada, el usuario ve una opción para mostrar los títulos durante una reunión.

<a name="bkcontentsharing"> </a>

## <a name="meeting-policy-settings---content-sharing"></a>Configuración de la directiva de reunión - uso compartido de contenido

- [Modo de uso compartido de pantalla](#screen-sharing-mode)
- [Permitir que un participante dar o solicitar el control](#allow-a-participant-to-give-or-request-control)
- [Permitir que un participante externo a proporcionar o solicitar el control](#allow-an-external-participant-to-give-or-request-control)
- [Permitir el uso compartido de PowerPoint](#allow-powerpoint-sharing)
- [Permitir la Pizarra](#allow-whiteboard)
- [Permitir notas compartidas](#allow-shared-notes)
- [Permitir charla en las reuniones (próximamente)](#allow-chat-in-meetings-coming-soon)

### <a name="screen-sharing-mode"></a>Modo de uso compartido de pantalla

Esto es una combinación de una directiva por usuario y por el organizador. Esta configuración controla si el escritorio o se permite el uso compartido de la ventana de reunión del usuario. Los participantes que no tienen las directivas asignadas de la reunión (por ejemplo, anónima, invitado, B2B y los participantes federados) heredan la directiva de organizador de la reunión.

|Valor de configuración |Comportamiento  |
|---------|---------|
|**Pantalla completa**    | Se permite el uso compartido de escritorio completa y uso compartido de aplicaciones de la reunión |
|**Aplicación de inicio único**   | Uso compartido de aplicaciones está permitido en la reunión        |
|**Deshabilitado**     |Uso compartido de la pantalla y uso compartido de aplicaciones desactivan en la reunión.       |

Veamos el ejemplo siguiente.

|Usuario |Directiva de reunión |Modo de uso compartido de pantalla |
|---------|---------|---------|
|Daniela  | Global   | Pantalla completa |
|Amanda   | Location1MeetingPolicy  | Deshabilitado |

Reuniones hospedadas por Daniela permitir que los participantes de la reunión compartir su pantalla completa o una aplicación específica. Si Amanda se une a la reunión de Daniela, Amanda no puede compartir su pantalla o una aplicación específica como su configuración de directiva está deshabilitada. En las reuniones hospedadas por Amanda, nadie se permite compartir su pantalla o una sola aplicación, independientemente de la directiva de modo que se les haya asignado de uso compartido de pantalla. Esto significa que Daniela no puede compartir su pantalla o una sola aplicación en las reuniones de Amanda.  

Actualmente, los usuarios no pueden reproducir vídeo o compartir su pantalla en una reunión de los equipos si utilizan Google Chrome.

### <a name="allow-a-participant-to-give-or-request-control"></a>Permitir que un participante dar o solicitar el control

Se trata de una directiva por usuario. Esta configuración controla si el usuario puede otorgar el control de la ventana o el escritorio compartido a otros participantes de la reunión. Para ceder el control, mantenga el mouse sobre la parte superior de la pantalla. 

Si esta opción está activada para el usuario, la opción de **Ceder el Control** se muestra en la barra superior en una sesión de uso compartido. 

![reunión-directivas-proporcionan-control.png](media/meeting-policies-give-control.png)

Si la configuración está desactivada para el usuario, la opción de **Ceder el Control** no está disponible.

![Meeting-Policies-Give-control-Not-Available.png](media/meeting-policies-give-control-not-available.png)

Veamos el ejemplo siguiente.

|Usuario |Directiva de reunión  |Permitir que otro participante dar o solicitar el control |
|---------|---------|---------|
|Daniela   | Global   | True       |
|Babek    | Location1MeetingPolicy        | False   |

Daniela puede ceder el control del escritorio compartido o la ventana a los demás participantes de una reunión organizada por Babek, mientras que Babek no puede ceder el control a otros participantes.

### <a name="allow-an-external-participant-to-give-or-request-control"></a>Permitir que un participante externo a proporcionar o solicitar el control

Se trata de una directiva por usuario. Esta configuración controla si los participantes externos en una reunión pueden ceder el control de su escritorio compartido o ventana a otros participantes de la reunión. Los participantes externos en las reuniones de los equipos se pueden clasificar como sigue:  

   - Usuario anónimo
   - Usuarios invitados  
   - Usuario de B2B
   - Usuario federado  

Si los usuarios federados pueden ceder el control a los usuarios externos mientras comparte se controla mediante la opción de **Permitir un participante externo a proporcionar o solicitar el control** de su organización.

### <a name="allow-powerpoint-sharing"></a>Permitir el uso compartido de PowerPoint

Se trata de una directiva por usuario. Esta configuración controla si el usuario puede compartir diapositivas de PowerPoint en una reunión. Los usuarios externos, incluidos los usuarios anónimos, invitados y federados, heredan la directiva de organizador de la reunión.

Veamos el ejemplo siguiente.

|Usuario |Directiva de reunión  |Permitir el uso compartido de PowerPoint |
|---------|---------|---------|
|Daniela   | Global   | True       |
|Amanda   | Location1MeetingPolicy        | False   |

Amanda no puede compartir diapositivas de PowerPoint en las reuniones, incluso si es el organizador de la reunión. Daniela puede compartir diapositivas de PowerPoint, incluso si la reunión está organizada por Amanda. Amanda puede ver diapositivas PowerPoint compartidos por otros usuarios en la reunión, aunque no puede compartir diapositivas de PowerPoint.

### <a name="allow-whiteboard"></a>Permitir la Pizarra

Se trata de una directiva por usuario. Esta configuración controla si un usuario puede compartir la Pizarra en una reunión. Los usuarios externos, incluidos anónimo, B2B y los usuarios federados, heredan la directiva de organizador de la reunión. 

Veamos el ejemplo siguiente.

|Usuario |Directiva de reunión  |Permitir la Pizarra|
|---------|---------|---------|
|Daniela   | Global   | True       |
|Amanda   | Location1MeetingPolicy        | False   |

Amanda no puede compartir la Pizarra en una reunión, incluso si es el organizador de la reunión. Daniela puede compartir la Pizarra, incluso si se organiza una reunión por Amanda.  

### <a name="allow-shared-notes"></a>Permitir notas compartidas

Se trata de una directiva por usuario. Esta configuración controla si un usuario puede crear y compartir notas en una reunión. Los usuarios externos, incluidos anónimo, B2B y los usuarios federados, heredan la directiva de organizador de la reunión. La ficha **Notas de reunión** actualmente es sólo compatibles en las reuniones tienen menos de 20 participantes. 

Veamos el ejemplo siguiente.

|Usuario |Directiva de reunión  |Permitir notas compartidas |
|---------|---------|---------|
|Daniela   | Global   | True       |
|Amanda   | Location1MeetingPolicy | False |

Daniela puede tomar notas en las reuniones de Amanda y Amanda no puede tomar notas en las reuniones.

### <a name="allow-chat-in-meetings-coming-soon"></a>Permitir charla en las reuniones (próximamente)

Se trata de una directiva por organizador. Esta configuración controla si se permite el chat de la reunión en reunión del usuario. 

<a name="bkparticipantsandguests"> </a>

## <a name="meeting-policy-settings---participants--guests"></a>Configuración de la directiva de reunión - invitados de & de los participantes

Esta configuración controla que esperar de participantes de la reunión en la sala de espera antes de que sean admitidos en la reunión y el nivel de participación se permiten en una reunión.

- [Admitir automáticamente las personas](#automatically-admit-people)
- [Permitir a los usuarios anónimos iniciar una reunión](#allow-anonymous-people-to-start-a-meeting)
- [Permitir a los usuarios de acceso telefónico para el desvío de la sala de espera](#allow-dial-in-users-to-bypass-the-lobby-coming-soon)
- [Permitir que los organizadores invalidar la configuración de la sala de espera](#allow-organizers-to-override-lobby-settings-coming-soon)

### <a name="automatically-admit-people"></a>Admitir automáticamente las personas

Se trata de una directiva por organizador. Esta configuración controla si unirse a una reunión directamente de personas o espera en la sala de espera hasta que se admitan por un usuario autenticado.

![reunión-directivas-lobby.png](media/meeting-policies-lobby.png)

 Los organizadores de reuniones pueden haga clic en **Opciones de reunión** en la invitación a la reunión para cambiar esta configuración para cada reunión que programan. **(próximamente)**
  
|Valor de configuración  |Unirse a comportamiento |
|---------|---------|
|**Todos**   |Todos los participantes de la reunión unirse a la reunión directamente sin esperar en la sala de espera. Esto incluye los usuarios autenticados, los usuarios federados, los invitados, los usuarios anónimos y las personas que se conectan por teléfono.       |
|**Todas las personas de su organización y de organizaciones federadas**     |Los usuarios autenticados dentro de la organización, incluidos los usuarios invitados y los usuarios de organizaciones federadas, unirse a la reunión directamente sin esperar en la sala de espera.  Los usuarios anónimos y los usuarios que se conectan por teléfono esperan en la sala de espera.   |
|**Todas las personas de su organización**    |Los usuarios autenticados desde dentro de la organización, incluidos los usuarios invitados, unirse a la reunión directamente sin esperar en la sala de espera.  Los usuarios federados, usuarios anónimos y usuarios que se conectan por teléfono esperan en la sala de espera.           |

### <a name="allow-anonymous-people-to-start-a-meeting"></a>Permitir a los usuarios anónimos iniciar una reunión

Se trata de una directiva por organizador. Esta configuración controla si usuarios anónimos, incluidos B2B y los usuarios federados, pueden unirse a reuniones del usuario sin un usuario autenticado de la organización de asistencia. 

![reunión-directivas-anónimos-usuario-lobby.png](media/meeting-policies-anonymous-user-lobby.png)

Aquí es el comportamiento de combinación de personas anónimos cuando los usuarios autenticados están presentes en la reunión.

|Permitir a los usuarios anónimos iniciar una reunión  |Admitir automáticamente las personas |Unirse a comportamiento de usuarios anónimos |
|---------|---------|---------|
|True    | Todos      | Unirse directamente a         |
|   | Todas las personas de su organización       | Sala de espera        |
|   | Todas las personas de su organización y de organizaciones federadas       | Sala de espera         |
|False    | Todos        | Unirse directamente a        |
|   | Todas las personas de su organización     | Sala de espera        |
|   | Todas las personas de su organización y de organizaciones federadas      | Sala de espera         |

Aquí es el comportamiento de combinación de personas anónimos cuando no hay usuarios autenticados están presentes en la reunión.

|Permitir a los usuarios anónimos iniciar una reunión |Admitir automáticamente las personas  |Unirse a comportamiento de usuarios anónimos |
|---------|---------|---------|
|True    | Todos      | Unirse directamente a         |
|   | Todas las personas de su organización       | Sala de espera        |
|   | Todas las personas de su organización y de organizaciones federadas       | Sala de espera         |
|False    | Todos        | Sala de espera. Los usuarios se admiten automáticamente cuando el primer usuario autenticado se une a la reunión.        |
|   | Todas las personas de su organización     |Sala de espera         |
|   | Todas las personas de su organización y de organizaciones federadas      | Sala de espera         |

### <a name="allow-dial-in-users-to-bypass-the-lobby-coming-soon"></a>Permitir a los usuarios de acceso telefónico para el desvío de la sala de espera (próximamente)

Se trata de una directiva por organizador. Esta configuración controla si las personas que se conectan por teléfono unirse a la reunión directamente o esperan en la sala de espera independientemente de la configuración **automáticamente admitir a personas** .

Este es el comportamiento de combinación de personas que se conectan por teléfono.

|Permitir a los usuarios de acceso telefónico para el desvío de la sala de espera  |Admitir automáticamente a los usuarios  |Unirse a comportamiento de personas que se conectan |
|---------|---------|---------|
|True    | Todos      | Unirse directamente a         |
|   | Todas las personas de su organización       | Unirse directamente a        |
|   | Todas las personas de su organización y de organizaciones federadas       | Unirse directamente a         |
|False    | Todos        | Unirse directamente a        |
|   | Todas las personas de su organización     |Sala de espera         |
|   | Todas las personas de su organización y de organizaciones federadas      | Sala de espera         |

### <a name="allow-organizers-to-override-lobby-settings-coming-soon"></a>Permitir que los organizadores invalidar la configuración de la sala de espera (próximamente)

Se trata de una directiva por organizador. Esta configuración controla si el organizador de la reunión puede invalidar la configuración de la sala de espera que un administrador establece en **admitir automáticamente personas** y **Permitir a los usuarios de acceso telefónico para el desvío de la sala de espera** al programar una reunión nueva. 

Los organizadores de reuniones pueden haga clic en **Opciones de reunión** en la invitación a la reunión para cambiar la configuración de la sala de espera para cada reunión que programan. 

Aquí es cómo esta configuración afecta a si el organizador de la reunión puede cambiar la configuración **automáticamente admitir a personas** para cada las programaciones del organizador de la reunión.

|Permitir que los organizadores invalidar la configuración de la sala de espera  |Admitir automáticamente las personas  |Comportamiento |
|---------|---------|---------|
|True    | Todos      | Organizador puede cambiar la configuración en cualquier otro valor. |
|   | Todas las personas de su organización       | Organizador puede cambiar la configuración en cualquier otro valor.|
|   | Todas las personas de su organización y de organizaciones federadas       | Organizador puede cambiarlo a cualquier otro valor.         |
|False    | Todos        | Organizador puede cambiar la configuración en cualquier otro valor.|
|   | Todas las personas de su organización     |Organizador puede cambiar la configuración para **todos los usuarios de la organización**. |
|   | Todas las personas de su organización y de organizaciones federadas      | Organizador no puede invalidar la configuración de la sala de espera. |

A continuación cómo esta configuración afecta a si el organizador de la reunión puede cambiar la configuración de **Permitir que los usuarios de acceso telefónico para el desvío de la sala de espera** para cada las programaciones del organizador de la reunión.
    
|Permitir que los organizadores invalidar la configuración de la sala de espera  |Permitir a los usuarios de acceso telefónico para el desvío de la sala de espera  |Comportamiento |
|---------|---------|---------|
|True    |  True        | Organizador puede cambiar la configuración en False.       |
|True      | False         | Organizador puede cambiar la configuración en True.        |
|False     | True        |Organizador puede cambiar la configuración en False.         |
|False      |False          |Organizador no puede invalidar la configuración de la sala de espera y no puede permitir a los usuarios de acceso telefónico para el desvío de la sala de espera de la reunión.        |

[Artículo completo](meeting-policies-in-teams.md)

## <a name="related-topics"></a>Temas relacionados
[Directivas de mensajería de los equipos](messaging-policies-in-teams.md)
