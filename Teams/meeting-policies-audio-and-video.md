---
title: Administrar directivas de reunión para audio y vídeo
ms.author: mabond
author: mkbond007
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.audioandvideo
- seo-marvel-apr2020
description: Aprenda a administrar la configuración de directivas de reuniones en Teams para audio y vídeo.
ms.openlocfilehash: ac5c58c00f5069638c087d04a033e8e0ff3d4822
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706850"
---
# <a name="meeting-policy-settings-for-audio--video"></a>Configuración de la directiva de reunión para vídeo & audio

<a name="bkaudioandvideo"> </a>
<a name="ndi"> </a>

En este artículo se describe la configuración de la directiva de reunión específica para el audio y el vídeo. Entre ellas se incluyen las siguientes:

- [Modo de audio IP](#mode-for-ip-audio)
- [Modo de vídeo IP](#mode-for-ip-video)
- [Vídeo IP](#ip-video)
- [Velocidad de bits multimedia (kb/s)](#media-bit-rate-kbs)
- [Modo de filtros de vídeo](#video-filters-mode)
- [Permitir la configuración personalizada del fondo](#allow-custom-background-settings)
- [Control de cámara de extremo lejano (FECC) para cámaras de zoom de inclinación de puntos (PTZ)](#far-end-camera-control-fecc-for-point-tilt-zoom-ptz-cameras)

### <a name="mode-for-ip-audio"></a>Modo de audio IP

Esta es una directiva por usuario. Esta configuración controla si se puede activar el audio en reuniones y llamadas de grupo. Estos son los valores de configuración.

|Valor de configuración |Comportamiento  |
|---------|---------|
|**Audio entrante y saliente activado**    |De forma predeterminada, se permiten en la reunión el vídeo y audio entrantes y salientes. |
|**No habilitado**     |El audio entrante y saliente en la reunión está desactivado.     |

Si se establece **en No habilitado** para un usuario, podrá programar y organizar reuniones, pero no podrá usar el audio. Para unirse a una reunión, tendrá que marcar para acceder a través de la red telefónica conmutada (RTC) o hacer que se llame a la reunión y unirse por teléfono a ella. Los participantes de la reunión que no tengan ninguna directiva asignada (por ejemplo, los participantes anónimos) tienen esto establecido como **Audio de salida y entrada habilitado** de forma predeterminada. En los clientes móviles de Teams, si esta configuración no está habilitada, el usuario tiene que llamar a la reunión a través de RTC.

Esta configuración no se aplica a las llamadas 1:1. Para restringir llamadas 1:1, configure una [directiva de llamada](teams-calling-policy.md) de Teams y desactive el valor **Realizar llamadas privadas**. Esta configuración tampoco se aplica a los dispositivos de la sala de conferencias, como los dispositivos de Surface Hub y Salas de Microsoft Teams.

Esta configuración aún no está disponible para entornos de Microsoft 365 Government Community Cloud (GCC), GCC High o Department of Defense (DoD).

Para obtener más información, consulte [Administrar el audio y el vídeo de los participantes de la reunión](#manage-audiovideo-for-meeting-participants).

### <a name="mode-for-ip-video"></a>Modo de vídeo IP

Esta es una directiva por usuario. Esta configuración controla si se puede activar el vídeo en reuniones y llamadas de grupo. Estos son los valores de configuración.

|Valor de configuración |Comportamiento  |
|---------|---------|
|**Vídeo entrante y saliente activado**    | Se permite el vídeo entrante y saliente en la reunión. Esta configuración es la predeterminada. |
|**No habilitado**     | El vídeo entrante y saliente en la reunión está desactivado. En los clientes para móvil de Teams, los usuarios no pueden compartir vídeos ni fotos en la reunión. <br><br>Tenga en cuenta que si el **modo de audio IP** no está habilitado, el **modo de vídeo IP** tampoco permanecerá habilitado.  |

Si se establece en **No habilitado** para un usuario, no podrá activar el vídeo ni ver vídeos compartidos por otros participantes de la reunión. Los participantes de la reunión que no tengan ninguna directiva asignada (por ejemplo, los participantes anónimos) tienen esto establecido como **Vídeo de salida y entrada habilitado** de forma predeterminada.

Esta configuración no se aplica a los dispositivos de la sala de conferencias, como los dispositivos de Surface Hub y Salas de Microsoft Teams.

Esta configuración aún no está disponible para entornos de Microsoft 365 Government Community Cloud (GCC), GCC High o Department of Defense (DoD).

> [!NOTE]
> Tenga en cuenta que esta configuración controla el vídeo saliente y el entrante, mientras que la configuración de **vídeo IP** controla el vídeo saliente. Para obtener más información, consulte [¿Cuál es la prioridad de la configuración de directiva de vídeo IP?](#which-ip-video-policy-setting-takes-precedence) y [Administrar el audio y el vídeo de los participantes de la reunión](#manage-audiovideo-for-meeting-participants).

Para obtener más información, consulte [Administrar el audio y el vídeo de los participantes de la reunión](#manage-audiovideo-for-meeting-participants).

### <a name="ip-video"></a>Vídeo IP

Esta es una combinación de directiva por organizador y por usuario. El vídeo es un componente clave de las reuniones. En algunas organizaciones, los administradores pueden querer disponer de más control sobre qué reuniones de usuarios tienen vídeo. Esta configuración controla si se puede activar el vídeo en reuniones hospedadas por un usuario y en llamadas 1:1 y de grupo iniciadas por un usuario. En los clientes móviles de Teams, esta configuración controla si los usuarios pueden compartir fotos y vídeos en una reunión.

Las reuniones organizadas por un usuario que tiene habilitada esta configuración de directiva, permiten el uso compartido de vídeo en la reunión por parte de los participantes de la reunión, si estos también tienen la configuración de directiva habilitada. Los participantes de la reunión a los que no se les ha asignado ninguna directiva (por ejemplo, los participantes anónimos y federados) heredan la directiva del organizador de la reunión.

> [!NOTE]
> Tenga en cuenta que esta configuración controla el vídeo saliente mientras que la configuración **Modo para vídeo IP** controla tanto el vídeo saliente como el entrante. Para obtener más información, consulte [¿Cuál es la prioridad de la configuración de directiva de vídeo IP?](#which-ip-video-policy-setting-takes-precedence) y [Administrar el audio y el vídeo de los participantes de la reunión](#manage-audiovideo-for-meeting-participants).

| Clientes de escritorio y web de Teams |Cliente móvil de Teams  |
|:-------:|:-------:|
|![Captura de pantalla que muestra información para unirse a la reunión y la configuración de audio o vídeo en el cliente de escritorio.](media/meeting-policies-audio-video-settings.png)    |![Captura de pantalla que muestra la pantalla para unirse a la reunión y la configuración de audio o vídeo en el cliente de móvil](media/meeting-policies-mobile-join.png)          |

Veamos el ejemplo siguiente.

|Usuario |Directiva de reuniones  |Vídeo IP |
|---------|---------|---------|
|Daniela   | Global   | Activado       |
|Amanda    | Location1MeetingPolicy        | Desactivado      |

Las reuniones hospedadas por Daniela permiten activar el vídeo. Daniela puede unirse a la reunión y activar el vídeo. Amanda no puede activar el vídeo en la reunión de Daniela porque la directiva de Amanda está configurada para no permitir el vídeo. Amanda pueden ver vídeos compartidos por otros participantes de la reunión.

En las reuniones hospedadas por Amanda, nadie puede activar el vídeo, independientemente de la directiva de vídeo que tenga asignada. Esto significa que Daniela no puede activar el vídeo en las reuniones de Amanda.  

Si Daniela llama a Amanda con el vídeo activado, Amanda puede responder a la llamada solo con audio.  Cuando se conecte la llamada, Amanda podrá ver el vídeo de Daniela, pero no podrá activar el vídeo. Si Amanda llama a Daniela, Daniela podrá responder a la llamada con vídeo o audio. Cuando se conecte la llamada, Daniela podrá activar o desactivar el vídeo, según lo vea necesario.

Para obtener más información, consulte [Administrar el audio y el vídeo de los participantes de la reunión](#manage-audiovideo-for-meeting-participants).

#### <a name="which-ip-video-policy-setting-takes-precedence"></a>¿Qué configuración de directiva de vídeo IP tiene prioridad?

Para un usuario, la configuración de directiva más restrictiva para el vídeo tiene prioridad. Por ejemplo:

|Vídeo IP|Modo de vídeo IP|Experiencia de reunión|
|---------|---------|---------|
|Organizador: **Activado**<br><br>Participante: **Activado** |Participante: **Deshabilitado**        |La configuración del **Modo de vídeo IP** tiene prioridad. El participante al que se asigna esta directiva no puede activar o ver vídeos compartidos por otros usuarios.|
|Organizador: **Activado**<br><br>Participante: **Activado** |Participante: **Vídeo entrante y saliente activado**          |El participante al que se asigna esta directiva puede activar o ver vídeos compartidos por otros usuarios.         |
|Organizador: **Activado**<br><br>Participante: **Desactivado** |Participante: **Vídeo entrante y saliente activado**         |La configuración de **vídeo IP** tiene prioridad. Los participantes solo pueden ver el vídeo entrante y no pueden enviar vídeo saliente.         |
|Organizador: **Activado**<br><br>Participante: **Desactivado** |Participante: **Deshabilitado**         |La configuración del **Modo de vídeo IP** tiene prioridad. El participante no puede ver ni el vídeo entrante ni el saliente.|
|Organizador: **Desactivado**    |       |La configuración de **vídeo IP** tiene prioridad porque está desactivada para el organizador. Nadie puede activar el vídeo en las reuniones organizadas por el usuario al que se asigna esta directiva.         |

### <a name="manage-audiovideo-for-meeting-participants"></a>Administrar el audio y el vídeo de los participantes de la reunión

|Si quiere...  |Establezca las siguientes configuraciones de directivas  |
|---------|---------|
|Deshabilitar el audio y el vídeo para los participantes en reuniones  |Modo de audio IP: **Deshabilitado**<br> Modo de vídeo IP: **Deshabilitado**<br>Vídeo IP: N/A       |
|Habilitar solo vídeo y audio entrante para participantes en reuniones  |Modo de audio IP: **Audio entrante y saliente activado**<br> Modo de vídeo IP: **Vídeo entrante y saliente activado**<br>Vídeo IP: **Desactivado**       |
|Deshabilitar el vídeo para los participantes en reuniones (los participantes solo tienen audio)|  Modo de audio IP: **Activar el audio entrante y saliente**<br> Modo de vídeo IP: **Deshabilitado**<br>Vídeo IP: N/A
|Habilitar el audio y el vídeo para los participantes en reuniones    |Modo de audio IP: **Audio entrante y saliente activado** (predeterminado)<br> Modo de vídeo IP: **Vídeo entrante y saliente activado** (predeterminado)<br>Vídeo IP: **Activado** (predeterminado)    |

Se aplica la directiva más restrictiva entre la directiva del organizador de la reunión y la del usuario. Por ejemplo, si un organizador tiene una directiva que restringe el vídeo y la directiva de un usuario no restringe el vídeo, los participantes de la reunión heredan la directiva del organizador de la reunión y no tienen acceso al vídeo en las reuniones. Esto significa que solo podrán unirse a la reunión con audio.

> [!NOTE]
> Cuando un usuario inicia una llamada de grupo para unirse por teléfono, no se muestra la pantalla **Usar teléfono para el audio**. Este es un problema conocido que estamos intentando resolver. Para solucionar este problema, seleccione **Audio del teléfono** en **Otras opciones para unirse**.

#### <a name="teams-mobile-clients"></a>Clientes de móvil de Teams

Para los usuarios de clientes móviles de Teams, la capacidad de compartir fotos y vídeos durante una reunión también viene determinada por la configuración del modo **de vídeo IP** o **ip** . En función de la configuración de directiva que tenga prioridad, la capacidad para compartir vídeos y fotos no estará disponible. Esto no afecta al uso compartido de la pantalla, que se configura con el modo de [Uso compartido de pantalla](meeting-policies-content-sharing.md#screen-sharing-mode). Asimismo, puede establecer una directiva de movilidad de [Teams](/powershell/module/skype/new-csteamsmobilitypolicy) para evitar que los usuarios móviles utilicen vídeo IP sobre una conexión móvil, lo que significa que deben usar una conexión Wi-Fi.

### <a name="media-bit-rate-kbs"></a>Velocidad de bits multimedia (kb/s)

Esta es una directiva por usuario. Esta configuración determina la velocidad de bits multimedia para las transmisiones por audio, vídeo y uso compartido de aplicaciones en vídeo en las llamadas y reuniones para el usuario. Se aplica a los usuarios de la llamada o reunión, en transferencias multimedia tanto de subida como de bajada. Esta configuración le ofrece un control en detalle de la administración de ancho de banda de su organización. Dependiendo de los escenarios de reuniones necesarios para los usuarios, le recomendamos que disponga del suficiente ancho de banda para disfrutar de una buena calidad. El valor mínimo es 30 kb/s y el valor máximo depende del escenario de la reunión. Para obtener más información sobre el ancho de banda mínimo recomendado para reuniones, llamadas y eventos en directo de buena calidad en Teams, vea [Requisitos de ancho de banda](prepare-network.md#bandwidth-requirements).

Si no hay suficiente ancho de banda para una reunión, los participantes ven un mensaje que indica que la calidad de la red es deficiente.

Para las reuniones que necesitan una experiencia de vídeo de mayor calidad, como las reuniones de juntas directivas y los eventos de Teams en directo, le recomendamos que establezca el ancho de banda en 10 Mb/s. Incluso si se establece la experiencia máxima, la pila de medios de Teams se adapta a condiciones de bajo ancho de banda cuando se detectan determinadas condiciones de red, según el contexto.

## <a name="video-filters-mode"></a>Modo de filtros de vídeo

<a name="bkvideofilters"> </a>

Esta es una directiva por usuario. Esta configuración controla si los usuarios pueden personalizar su fondo de vídeo en una reunión.

Puede usar el Centro de administración de Teams y PowerShell para establecer esta directiva. Para editar una directiva de reunión de Teams existente, use el cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy). También puede crear una nueva directiva de reunión de Teams con el cmdlet [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) y asignarla a los usuarios.

Para especificar si los usuarios pueden personalizar el fondo del vídeo en una reunión, establezca el parámetro **VideoFiltersMode** (**configuración Seleccionar filtros de vídeo** en el Centro de administración de Teams) de la siguiente manera:

|Establecer valor en PowerShell|Valor de configuración en el Centro de administración de Teams |Comportamiento  |
|---------|---------|---------|
|**NoFilters** |**Sin filtro**    |El usuario no puede personalizar su fondo de vídeo.|
|**BlurOnly**     |**Solo difuminado de fondo**|El usuario tiene la opción de difuminar el fondo de vídeo. |
|**BlurandDefaultBackgrounds**|**Desenfoque de fondo e imágenes predeterminadas**     |El usuario tiene la opción de difuminar su fondo de vídeo o elegir un conjunto de imágenes predeterminado para usarlo como fondo. |
|**AllFilters**|**Todos los filtros**     |El usuario tiene la opción de difuminar su fondo de vídeo, elegir entre un conjunto de imágenes predeterminado o cargar una imagen personalizada para usarla como fondo. |

> [!NOTE]
> Teams no puede filtrar las imágenes cargadas por los usuarios. Al usar la configuración **AllFilters**, debe tener directivas de organización internas para evitar que los usuarios puedan cargar imágenes ofensivas, inadecuadas, o para las cuales la organización no tenga derechos de uso en el contexto de fondos para reuniones de Teams.

### <a name="allow-custom-background-settings"></a>Permitir la configuración personalizada del fondo

Puede agregar imágenes de fondo personalizadas para que se usen por inquilino. Esta característica permite a las empresas aplicar personalización de marca corporativa a las reuniones de Teams.

1. Inicie la sesión en el Centro de administración de Teams

2. Seleccione **Directivas de** > **reunión de** >  reuniones **Personalizar imágenes de reunión**.

   ![Selección de directivas de reunión con el botón Personalizar imágenes de la reunión resaltado.](media/custom-background-image-button.png)

3. Seleccione **Activado en** **imágenes de fondo de toda la organización**.

4. Seleccione **+ Agregar imágenes**.

5. En el panel Administrar fondos, selecciona **Agregar imagen**.

6. Asegúrese de que las imágenes cumplen estos requisitos:
  
   - Tamaño mínimo de 360 px
   - Tamaño máximo 2048 px
   - Tipo de archivo PNG, JPG o BMP
   - Se pueden cargar un máximo de 50 imágenes

7. Obtenga una vista previa de las imágenes que ha seleccionado y, a continuación, seleccione **Cerrar**.

8. Revise las imágenes y agregue más según sea necesario.

9. Seleccione **Guardar**.

Los asistentes a la reunión verán una selección de imágenes de fondo que pueden usar cuando asistan a una reunión.

> [!NOTE]
> Los cambios pueden tardar hasta 24 horas en surtir efecto.

> [!NOTE]
> Esta característica está disponible temporalmente en la versión preliminar pública para todos los clientes de Microsoft Teams. Para obtener esta característica después de la vista previa, cada usuario necesitará la licencia del complemento Comunicaciones avanzadas. Para más información, consulte [Complemento de Comunicaciones avanzadas para Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).

### <a name="far-end-camera-control-fecc-for-point-tilt-zoom-ptz-cameras"></a>Control de cámara de extremo lejano (FECC) para cámaras de zoom de inclinación de puntos (PTZ)

El control de cámara de extremo lejano es una directiva que se puede asignar a Salas de Teams en cuentas de recursos de Windows. Permite que las cámaras PTZ conectadas a una sala de Teams sean controladas por los participantes de la reunión en la aplicación cliente de Teams durante las reuniones.

Para usar el control de cámara de extremo lejano, los participantes de la reunión tendrán que obtener la aplicación **Controles de cámara PTZ** .  Consulte [Permitir y bloquear aplicaciones](manage-apps.md#allow-and-block-apps) para obtener información sobre cómo hacer que la aplicación esté disponible en la tienda de aplicaciones de su organización.

Para especificar quién puede usar el control de cámara de extremo lejano en una reunión, cree y asigne una nueva directiva a una cuenta de recursos de Salas de Teams mediante el cmdlet [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy?view=skype-ps) o use [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) para modificar una existente. Establezca el `TeamsCameraFarEndPTZMode` parámetro en uno de los siguientes valores:

| Valor de configuración | Comportamiento |
|---------------|----------|
|Deshabilitado | Esta configuración es la predeterminada. Cuando se establece en "deshabilitado", nadie puede usar controles de cámara PTZ. |
|AutoAcceptAll | Los controles de la cámara PTZ están disponibles automáticamente para cualquier participante de la reunión. |
|AutoAcceptInTenant | Los controles de la cámara PTZ solo están disponibles automáticamente para los participantes de la misma organización que la sala de Teams. |

Cuando `TeamsCameraFarEndPTZMode` se establece en `AutoAcceptAll` o `AutoAcceptInTenant`, el control de la cámara puede desactivarse manualmente desde la sala de Teams en cualquier momento durante una reunión. El control de la cámara tampoco está disponible cuando la cámara está desactivada.

Cualquier cámara con controles mecánicos PTZ y UVC es compatible. Para obtener una lista de las cámaras certificadas para Teams, incluidas las cámaras PTZ y las que no son PTZ, consulte [Versiones certificadas de firmware para periféricos de audio y vídeo USB](rooms/requirements.md#certified-firmware-versions-for-usb-audio-and-video-peripherals). Esta característica aún no es compatible con las cámaras con controles PTZ digitales ni con Salas de Teams en Android.  

> [!NOTE]
> Actualiza el firmware de la cámara antes de probar los controles PTZ. Consulta la documentación del fabricante de equipos originales (OEM) para actualizar el firmware.

## <a name="related-topics"></a>Temas relacionados

- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
- [Asignar directivas a los usuarios en Teams](policy-assignment-overview.md)
