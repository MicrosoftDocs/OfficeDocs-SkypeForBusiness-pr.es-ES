---
title: Grabación de reuniones en la nube de Teams
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
ms.reviewer: nakulm
search.appverid: MET150
localization_priority: Priority
f1.keywords:
- NOCSH
description: Guía práctica para implementar las características de voz en la nube en Teams para grabar reuniones de Teams y llamadas de grupo para capturar la actividad de audio, vídeo y uso compartido de la pantalla.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1ad5cb2c6bd1abd394d23d68c6636274a6cd1447
ms.sourcegitcommit: 79d20fa2c45173d5a990551e79571caff06d7f82
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2021
ms.locfileid: "53486150"
---
# <a name="teams-cloud-meeting-recording"></a>Grabación de reuniones en la nube de Teams

En Microsoft Teams, los usuarios pueden grabar sus reuniones y llamadas de grupo de Teams para capturar el audio, el vídeo y la actividad de pantalla compartida. Además, hay una opción para que las grabaciones tengan una transcripción automática, para que los usuarios puedan reproducir grabaciones de reunión con subtítulos y revisar elementos de discusión importantes en la transcripción. La grabación tiene lugar en la nube y se guarda en Microsoft OneDrive para la Empresa y Microsoft SharePoint Online, para que los usuarios puedan compartirla de forma segura en la organización.

Cuando se graba una reunión, sucede lo siguiente automáticamente:

- Se carga en OneDrive para la Empresa o en SharePoint Online
- Se asignan permisos de la grabación a las personas invitadas a la reunión
- Se incluye un vínculo a la grabación en el chat de la reunión
- La grabación se muestra en la pestaña Grabaciones y transcripciones de la reunión en el calendario de Teams
- Se agrega a varias listas de archivos en Microsoft 365: Compartidos conmigo, office.com, Recomendado, Reciente, etc.
- Se indexa para la búsqueda de Microsoft 365

Relacionado: [Documentación de usuario final de grabación de reuniones de Teams](https://aka.ms/recordmeeting)

>[!Note]
> El cambio del uso de Microsoft Stream (clásico) a OneDrive para la Empresa y SharePoint Online para grabaciones de reuniones se producirá automáticamente en agosto de 2021. Para obtener información detallada, consulte [Usar OneDrive para la Empresa y SharePoint Online o Stream para las grabaciones de reuniones](tmr-meeting-recording-change.md).

> [!NOTE]
> Para obtener más información sobre el uso de los roles en reuniones de Teams y cómo cambiar los roles de los usuarios, consulte [roles en una reunión de Teams](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us). Para ver las opciones de grabación de eventos en directo, consulte [Directivas de grabación de eventos en directo en Teams](teams-live-events/live-events-recording-policies.md).

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Requisitos previos para grabación de reuniones en la nube de Teams

Para que se graben las reuniones de un usuario de Teams, OneDrive para la Empresa y SharePoint Online deben estar habilitados para el espacio empresarial. Además, son necesarios los siguientes requisitos previos tanto para el organizador de la reunión como para la persona que inicia la grabación:

- El usuario debe tener suficiente almacenamiento en OneDrive para la Empresa para que se guarden las grabaciones de reuniones que no sean del canal.

- El canal de Teams debe tener suficiente almacenamiento en SharePoint Online para que se guarden las grabaciones de reuniones del canal.

- El usuario debe tener la configuración `CsTeamsMeetingPolicy -AllowCloudRecording` establecida en true para grabar reuniones y llamadas grupales.

- El usuario debe tener la configuración `CsTeamsCallingPolicy -AllowCloudRecordingForCalls` establecida en true para grabar llamadas individuales.

- El usuario no debe ser un usuario anónimo, invitado o federado en la reunión.

- Para habilitar la transcripción de la reunión de un usuario, la directiva de reunión de Teams a la que el usuario esté asignado debe tener la configuración `-AllowTranscription` establecida en true.

- Para permitir que las grabaciones de reuniones de canal se guarden de manera que los miembros del canal no puedan editar o descargar las grabaciones, la configuración `CSTeamsMeetingPolicy -ChannelRecordingDownload` debe establecerse en Bloquear.

> [!IMPORTANT]
>
> Los usuarios no necesitarán tener habilitado OneDrive para la Empresa o SharePoint Online si desea que los usuarios solo puedan grabar y descargar las grabaciones. Esto significa que las grabaciones no se almacenan en OneDrive para la Empresa o SharePoint Online, sino en el almacenamiento temporal de Teams con un límite de 21 días antes de que se eliminen. Esto no es algo que un administrador pueda controlar, administrar o eliminar en estos momentos.
>
> Para más [información sobre cómo funciona el almacenamiento temporal de grabación de reuniones](#temp-storage), consulte la información que se ofrece a continuación.  

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>Configurar la grabación de reuniones en la nube de Teams para los usuarios de su organización

En esta sección se explica cómo puede configurar y planear la grabación de reuniones de Teams a través de [directivas de reunión de Teams](./assign-policies.md).

### <a name="turn-on-or-turn-off-cloud-recording"></a>Activar o desactivar la grabación en la nube

Puede usar el centro de administración de Microsoft Teams o PowerShell para establecer una directiva de reunión de Teams para controlar si se pueden grabar las reuniones del usuario.

En el centro de administración de Microsoft Teams, active o desactive la opción **Permitir la grabación en la nube** en la directiva de reunión. Para más información, consulte [Configuración de la directiva de reunión para audio y vídeo](meeting-policies-audio-and-video.md#allow-cloud-recording).

Con PowerShell, configure la opción AllowCloudRecording en TeamsMeetingPolicy. Para obtener más información, consulte [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) y [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

Tenga en cuenta que tanto el organizador de la reunión como el iniciador la grabación necesitan tener permisos de grabación para grabar la reunión. A menos que haya asignado una directiva personalizada a los usuarios, a estos se les aplicará la directiva global, que tiene AllowCloudRecording habilitada de forma predeterminada.

> [!NOTE]
> Para obtener más información sobre el uso de los roles en Teams para configurar quién tiene permiso para grabar una reunión, vea [roles en una reunión de Teams](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).

Para que un usuario revierta a la directiva global, use el siguiente cmdlet para quitar una asignación de directiva específica para un usuario:

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

Para cambiar el valor de AllowCloudRecording en la directiva global, use el siguiente cmdlet:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $true
```

|Escenario|Pasos|
|--|--|
| Quiero que todos los usuarios de mi empresa puedan grabar sus reuniones. | <ol><li>Confirmar que CsTeamsMeetingPolicy global tiene AllowCloudRecording = True.<li>Todos los usuarios tienen CsTeamsMeetingPolicy global o una de las directivas de CsTeamsMeetingPolicy con AllowCloudRecording = True.</ol> |
| Quiero que la mayoría de los usuarios puedan grabar sus reuniones, pero quiero deshabilitar de forma selectiva usuarios específicos a los que no se les permite grabar. | <ol><li>Confirmar que GlobalCsTeamsMeetingPolicy tiene AllowCloudRecording = True.<li>La mayoría de los usuarios tienen CsTeamsMeetingPolicy global o una de las directivas de CsTeamsMeetingPolicy con AllowCloudRecording = True.<li>A los demás usuarios se les ha otorgado una de las directivas CsTeamsMeetingPolicy con AllowCloudRecording = False.</ol> |
| Quiero deshabilitar la grabación al 100%. | <ol><li>Confirmar que CsTeamsMeetingPolicy global tiene AllowCloudRecording = False.<li>A todos los usuarios se les ha otorgado la CsTeamsMeetingPolicy global o una de las directivas de CsTeamsMeetingPolicy con AllowCloudRecording = False. |
| Quiero que la grabación esté deshabilitada para la mayoría de los usuarios, pero permitir de forma selectiva qué usuarios específicos pueden grabar. | <ol><li>Confirmar que CsTeamsMeetingPolicy global tiene AllowCloudRecording = False.<li>A la mayoría de los usuarios se les ha otorgado la CsTeamsMeetingPolicy global o una de las directivas de CsTeamsMeetingPolicy con AllowCloudRecording = False.<li>Todos los demás usuarios tienen asignada una de las directivas de CsTeamsMeetingPolicy con AllowCloudRecording = True. <ol> |


<a name="bd-channel"></a>
### <a name="block-or-allow-download-of-channel-meeting-recordings"></a>Bloquear o permitir la descarga de grabaciones de reuniones de canal

Esta configuración controla si las reuniones de canal se guardan en una carpeta "Grabaciones" o en una carpeta "Solo grabaciones\Ver" en el canal.

Los dos valores de esta configuración son los siguientes:

- **Permitir** (valor predeterminado): guarda las grabaciones de reuniones del canal en una carpeta "Grabaciones" del canal. Los permisos de los archivos de grabación se basarán en los permisos de SharePoint Online de canal. Es igual que cualquier otro archivo cargado para el canal.

- **Bloquear**: guarda las grabaciones de reuniones del canal en una carpeta "Grabaciones\Ver solo" del canal. Los propietarios del canal tendrán derechos completos sobre las grabaciones de esta carpeta, pero los miembros del canal tendrán acceso de lectura sin capacidad de descarga.

Con PowerShell, puede configurar la opción ChannelRecordingDownload en TeamsMeetingPolicy. Para obtener más información, consulte [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) y [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

A menos que haya asignado una directiva personalizada a los usuarios, a estos se les aplicará la directiva global, que tiene ChannelRecordingDownload establecida en Permitir de forma predeterminada.

Para que un usuario revierta a la directiva global, use el siguiente cmdlet para quitar una asignación de directiva específica para un usuario:

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

Para cambiar el valor de ChannelRecordingDownload en la directiva global, use el siguiente cmdlet:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -ChannelRecordingDownload Block
```

> [!NOTE]
> La configuración ChannelRecordingDownload solo está disponible en la versión preliminar 2.4.1 o posterior del módulo de PowerShell de Teams. Para descargar la versión preliminar más reciente del módulo, use este comando:
>
>```powershell
>Install-Module -Name MicrosoftTeams -Force -AllowClobber -AllowPrerelease
>```

### <a name="turn-on-or-turn-off-recording-transcription"></a>Activar o desactivar la transcripción de grabaciones

Esta configuración controla si se pueden usar las características de subtítulos y transcripción durante la reproducción de las grabaciones de la reunión. Si desactiva esta opción, las opciones de **Búsqueda** y **CC** no estarán disponibles durante la reproducción de la grabación de una reunión. La persona que ha iniciado la grabación necesita que esta opción esté activada para que la grabación también incluya transcripción.

> [!NOTE]
> Actualmente, la transcripción de reuniones grabadas solo es compatible con los usuarios que tengan el idioma de los equipos en inglés y cuando se habla inglés en la reunión. Se almacenan junto con las grabaciones de reuniones en OneDrive para la Empresa y el almacenamiento en la nube de SharePoint Online.

Puede usar el centro de administración de Microsoft Teams o PowerShell para establecer una directiva de reunión de Teams para controlar si el iniciador de la reunión tiene la opción de transcribir la grabación de la reunión.

En el centro de administración de Microsoft Teams, active o desactive la opción **Permitir transcripción** en la directiva de reunión. Para más información, consulte [Configuración de la directiva de reunión para audio y vídeo](meeting-policies-audio-and-video.md#allow-transcription).

Con PowerShell, configure la opción AllowTranscription en TeamsMeetingPolicy. Para obtener más información, consulte [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) y [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

A menos que haya asignado una directiva personalizada a los usuarios, los usuarios recibirán la directiva global, que tiene AllowTranscription deshabilitada de forma predeterminada.

Para que un usuario revierta a la directiva global, use el siguiente cmdlet para quitar una asignación de directiva específica para un usuario:

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

Para cambiar el valor de AllowCloudRecording en la directiva global, use el siguiente cmdlet:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $false
```

</br>
</br>

|Escenario|Pasos |
|---|---|
|Quiero que todos los usuarios de mi empresa puedan transcribir cuando inician la grabación de una reunión. |<ol><li>Confirmar que CsTeamsMeetingPolicy global tiene AllowTranscription = True. <li>Todos los usuarios tienen csTeamsMeetingPolicy global o una de las directivas de CsTeamsMeetingPolicy con AllowTranscription = True </ol>|
|Quiero que la mayoría de los usuarios puedan transcribir las grabaciones de las reuniones, pero deshabilitar de forma selectiva usuarios específicos a los que no se les permita transcribir. |<ol><li>Confirmar que CsTeamsMeetingPolicy global tiene AllowTranscription = True. <li>La mayoría de los usuarios tienen CsTeamsMeetingPolicy global o una de las directivas de CsTeamsMeetingPolicy con AllowTranscription = True. <li>A los demás usuarios se les ha otorgado una de las directivas de CsTeamsMeetingPolicy con AllowTranscription = False. </ol>|
|Quiero que la transcripción de la grabación se deshabilite al 100%. |<ol><li>Confirmar que CsTeamsMeetingPolicy global tiene AllowTranscription = False. <li>A todos los usuarios se les ha otorgado la CsTeamsMeetingPolicy global o una de las directivas de CsTeamsMeetingPolicy con AllowTranscription = False. </ol>|
|Quiero que la transcripción esté deshabilitada para la mayoría de los usuarios, pero permitir de forma selectiva que determinados usuarios puedan transcribir. |<ol><li>Confirmar que CsTeamsMeetingPolicy global tiene AllowCloudRecording = False. <li>A la mayoría de los usuarios se les ha otorgado la CsTeamsMeetingPolicy global o una de las directivas de CsTeamsMeetingPolicy con AllowCloudRecording = False. <li>Todos los demás usuarios tienen asignada una de las directivas de CsTeamsMeetingPolicy con AllowCloudRecording = True. </ol>|


## <a name="permissions-and-storage"></a>Permisos y almacenamiento

Las grabaciones de reuniones se almacenan en OneDrive para la Empresa y en el almacenamiento en la nube de SharePoint Online. La ubicación y los permisos dependen del tipo de reunión y del rol del usuario en la reunión. A continuación, se enumeran los permisos predeterminados aplicados a la grabación. Los usuarios que tienen todos los derechos de edición sobre el archivo de grabación de vídeo pueden cambiar los permisos y compartir el archivo más adelante con otros usuarios según sea necesario.

### <a name="non-channel-meetings"></a>Reuniones que no son de canal

- La grabación se almacena en una carpeta denominada **Grabaciones** en OneDrive para la Empresa del usuario que ha hecho clic en Grabar. 

  Por ejemplo: <i>OneDrive para la Empresa de la persona que inició la grabación</i>/**Grabaciones**

- A las personas invitadas a la reunión —excepto los usuarios externos— se les concederá automáticamente permiso para el archivo de la grabación con acceso de vista y sin capacidad de descarga.

- El propietario de la reunión y la persona que ha hecho clic en Grabar obtendrán acceso de edición completo con la capacidad de cambiar los permisos y de compartir con otras personas.

### <a name="channel-meetings"></a>Reuniones de canal

Si `Set-CsTeamsMeetingPolicy -ChannelRecordingDownload` está establecido en Permitir (valor predeterminado):

- La grabación se almacena en la biblioteca de documentación del sitio de Teams, en una carpeta denominada **Grabaciones**. 

  Ejemplo: <i>Nombre de Teams: nombre del canal</i>/**Documentos**/**Grabaciones**

- El miembro que hizo clic Grabar tiene derechos de edición de la grabación.

- Los permisos de todos los demás miembros se basan en los permisos de SharePoint Online del canal.

Si `Set-CsTeamsMeetingPolicy -ChannelRecordingDownload` se establece en Bloquear:

- La grabación se almacena en la biblioteca de documentación del sitio de Teams, en una carpeta denominada **Grabaciones/Ver solo**. 

  Ejemplo: <i>nombre de Teams: nombre del canal</i>/**Documentos/Grabaciones/Ver solo**

- Los propietarios del canal tendrán derechos completos de edición y de descarga sobre las grabaciones de esta carpeta.

- Los miembros del canal tendrán acceso de solo vista sin capacidad de descarga.

Para más información sobre tipos de reunión específicos, consulte la tabla siguiente:

| Tipo de reunión  | ¿Quién ha hecho clic en Grabar?| ¿Dónde está la grabación? | ¿Quién tiene acceso? R/W, R o uso compartido  |
|-------------|-----------------------|------------------------|------------------------|
|Llamada uno a uno con partes internas             |Autor de la llamada                 |Cuenta de OneDrive para la Empresa del autor de la llamada                        |El autor de la llamada es propietario y tiene todos los derechos. <br /><br />El destinatario (si está en el mismo espacio empresarial) tiene acceso de solo lectura. Sin acceso de uso compartido. <br /><br /> El destinatario (si está en otro espacio empresarial) no tiene acceso. El autor de la llamada debe compartirlo con el destinatario.|
|Llamada uno a uno con partes internas             |Destinatario                 |Cuenta de OneDrive para la Empresa del destinatario                        |El destinatario es propietario y tiene todos los derechos. <br /><br />El autor de la llamada (si está en el mismo espacio empresarial) tiene acceso de solo lectura. Sin acceso de uso compartido. <br /><br />El autor de la llamada (si está en otro espacio empresarial) no tiene acceso. El destinatario debe compartirlo con el autor de la llamada.|
|Llamada uno a uno con llamada externa             |Autor de la llamada                 |Cuenta de OneDrive para la Empresa del autor de la llamada                        |El autor de la llamada es propietario y tiene todos los derechos.<br /> <br />El destinatario no tiene acceso. El autor de la llamada debe compartirlo con el destinatario.|
|Llamada uno a uno con llamada externa             |Destinatario                 |Cuenta de OneDrive para la Empresa del destinatario                        |El destinatario es propietario y tiene todos los derechos.<br /><br />El autor de la llamada no tiene acceso. El destinatario debe compartirlo con el autor de la llamada.|
|Llamada grupal                                 |Cualquier miembro de la llamada |El miembro del grupo que hizo clic en la cuenta de OneDrive para la Empresa de la grabación  |El miembro que hizo clic en la grabación tiene todos los derechos. <br /><br /> Otros miembros del mismo espacio empresarial tienen derechos de lectura. <br /><br /> Los miembros de grupo de otros espacios empresariales no tienen derechos sobre la grabación.|
|Reunión programada/adhoc                    |Organizador              |Cuenta de OneDrive para la Empresa del organizador                     |El organizador tiene todos los derechos de la grabación. <br /><br /> El resto de los miembros de la reunión tienen acceso de lectura sin capacidad de descarga.|
|Reunión programada/adhoc                    |Otro miembro de la reunión   |El miembro de la reunión que hizo clic en la grabación                                  |El miembro que hizo clic en la grabación tiene todos los derechos de la grabación. <br /><br />El organizador tiene derechos de edición y puede compartir.<br /><br /> El resto de los miembros de la reunión tienen acceso de lectura sin capacidad de descarga.|
|Reunión programada/addhoc con usuarios externos|Organizador              |Cuenta de OneDrive para la Empresa del organizador                     |El organizador tiene todos los derechos de la grabación.<br /> <br /> Todos los demás miembros de la reunión del mismo espacio empresarial que el organizador tienen acceso de lectura sin capacidad de descarga. <br /><br /> Todos los demás miembros externos no tienen acceso y el organizador debe compartirlo.|
|Reunión programada/addhoc con usuarios externos|Otro miembro de la reunión   |El miembro que hizo clic en la grabación                                  |El miembro que hizo clic en la grabación tiene todos los derechos de la grabación. El organizador tiene derechos de edición y puede compartir. <br /><br /> Todos los demás miembros de la reunión del mismo espacio empresarial que el organizador tienen acceso de lectura sin capacidad de descarga. <br /><br />Todos los demás miembros externos no tienen acceso y el organizador debe compartirlo.|
|Reunión de canal                            |Miembro de canal         |Ubicación de SharePoint Online de Teams para ese canal                   |Si Set-CsTeamsMeetingPolicy -ChannelRecordingDownload está establecido en Permitir (valor predeterminado), el miembro que ha hecho clic en Grabar tiene derechos de edición sobre la grabación. Los permisos de todos los demás miembros se basan en los permisos de SharePoint Online del canal.<Br><Br>Si Set-CsTeamsMeetingPolicy -ChannelRecordingDownload está establecido en Bloquear, los propietarios del canal tendrán derechos completos sobre la grabación, pero los miembros del canal tendrán acceso de lectura sin capacidad de descarga.|

<a name="temp-storage"></a>
### <a name="temporary-storage-when-unable-to-upload-to-onedrive-for-business-and-sharepoint-online"></a>Almacenamiento temporal cuando no se puede cargar en OneDrive para la Empresa y SharePoint Online

Si una grabación de reunión no se puede cargar en OneDrive para la Empresa y SharePoint Online, estará disponible temporalmente para su descarga desde Teams durante 21 días antes de que se elimine. En estos momentos, no es algo que un administrador pueda controlar o administrar, incluida la capacidad de eliminarlo.

Las grabaciones de reuniones pueden acabar en este almacenamiento temporal por los siguientes motivos:

- Para reuniones que no son de canal, si la grabación del usuario no tiene una configuración de OneDrive para la Empresa o si OneDrive para la Empresa ha alcanzado su cuota de almacenamiento
- Para una reunión de canal, si el sitio de SharePoint Online ha alcanzado su cuota de almacenamiento o si el sitio aún no se ha aprovisionado
- Si se habilitan directivas específicas de OneDrive para la Empresa y SharePoint Online que limiten a los usuarios la carga de archivos cuando no se encuentran en intervalos IP específicos, etc.

La retención de la grabación para este almacenamiento temporal se ve afectada por el propio mensaje de chat. Por lo tanto, cualquier eliminación del mensaje de chat original de la grabación impedirá que los usuarios puedan acceder a la grabación. Hay dos escenarios que pueden influenciar esta situación:

- **El usuario elimina de forma manual el mensaje de chat**: en este escenario, dado que el mensaje original no existe, los usuarios ya no podrán acceder a la grabación y no se podrán realizar más descargas. Sin embargo, la grabación en sí puede conservarse dentro de los sistemas internos de Microsoft durante un tiempo (sin superar el período original de 21 días).

- **La directiva de retención de chat elimina el mensaje de chat de la grabación**: las grabaciones de almacenamiento temporal están asociadas directamente a la directiva de retención de chat. Por lo tanto, las grabaciones del almacenamiento temporal de Teams se retendrán de forma predeterminada durante 21 días antes de eliminarse. Sin embargo, si el mensaje de chat se elimina antes del período de 21 días, la grabación también se eliminará debido a las directivas de retención de mensajes de chat. Después de esto, no se puede recuperar la grabación.

### <a name="planning-for-storage"></a>Planificación de almacenamiento

El tamaño de una grabación de 1 hora es de 400 MB. Asegúrese de entender la capacidad necesaria para los archivos grabados y de disponer de suficiente espacio de almacenamiento en OneDrive para la Empresa y en SharePoint Online.  Consulte [Establecer el espacio de almacenamiento predeterminado para OneDrive para la Empresa](/onedrive/set-default-storage-space) y [Administrar los límites de almacenamiento del sitio de SharePoint Online](/sharepoint/manage-site-collection-storage-limits) para comprender el almacenamiento base incluido en la suscripción y cómo comprar almacenamiento adicional.

## <a name="manage-meeting-recordings"></a>Administrar grabaciones de reuniones

Las grabaciones de reuniones se almacenan como archivos de vídeo en OneDrive para la Empresa y SharePoint Online y siguen las opciones de administración y gobernanza disponibles en dichas plataformas. Consulte [Información general sobre la gobernanza de SharePoint Online](/sharepoint/governance-overview), [Guía empresarial de OneDrive para la Empresa](/onedrive/plan-onedrive-enterprise)o [Guía para pequeñas empresas de OneDrive para la Empresa](/onedrive/one-drive-quickstart-small-business) para más información.

En el caso de las reuniones que no son de canal, las grabaciones se almacenan en OneDrive para la Empresa, por lo que el control de la propiedad y de la retención después de que un empleado abandone la empresa seguirá el [proceso normal de OneDrive para la Empresa y SharePoint Online](/onedrive/retention-and-deletion#the-onedrive-deletion-process).

## <a name="closed-captions-for-recordings"></a>Subtítulos para las grabaciones

Los subtítulos para las grabaciones de reuniones de Teams solo estarán disponibles durante la reproducción si el usuario tenía activada la transcripción en el momento de la grabación. Los administradores deben [activar la transcripción de la grabación a través de la directiva](#turn-on-or-turn-off-recording-transcription) para asegurarse de que los usuarios tengan la opción de grabar reuniones con transcripción.

Los subtítulos ayudan a crear contenido inclusivo para espectadores de todas las capacidades. Como propietario, puede ocultar los subtítulos en la grabación de la reunión, aunque la transcripción de la reunión seguirá estando disponible en Teams a menos que la elimine de allí.

En estos momentos, los subtítulos del archivo de vídeo de la grabación están vinculados a la transcripción de la reunión de Teams. En la mayoría de los casos, este vínculo se conservará mientras que el archivo siga existiendo, pero se puede romper si el archivo de vídeo se copia en el mismo OneDrive para la Empresa o sitio de SharePoint Online, lo que provocaría que los subtítulos no estén disponibles en el archivo de vídeo copiado.

Cualquier cambio futuro que se realice en el vínculo entre la transcripción en Teams y la grabación se explica aquí y en las notificaciones del centro de mensajes. Si se realiza cualquier cambio en el futuro, nos aseguraremos de que los archivos de grabación con menos de 60 días de antigüedad muestren la transcripción de la reunión como subtítulos.

> [!NOTE]
> Los subtítulos estarán solo en inglés (la transcripción de reuniones aún no está disponible en GCC).

## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>Cumplimiento y eDiscovery para grabaciones de reuniones

### <a name="ediscovery"></a>eDiscovery

Las grabaciones de reuniones se almacenan en OneDrive para la Empresa y SharePoint Online, lo cual es compatible con el nivel D de Microsoft 365 y Office 365. El mensaje de grabación completa se encuentra disponible en la función de búsqueda de contenido de cumplimiento de Microsoft Teams para admitir las solicitudes de eDiscovery para administradores de cumplimiento que estén interesados en las grabaciones de reuniones o de llamadas. Los administradores de cumplimiento pueden buscar la palabra clave "grabación" en la línea de asunto del elemento en la vista previa de búsqueda de contenido de cumplimiento y detectar grabaciones de reuniones y llamadas en la organización.

Además, el archivo de vídeo de grabación de reuniones se puede encontrar mediante búsquedas en eDiscovery de archivos en SharePoint Online y OneDrive para la Empresa.

Para más información sobre eDiscovery, consulte el artículo [Soluciones de eDiscovery para Microsoft 365](/microsoft-365/compliance/ediscovery)

### <a name="retention-policies"></a>Directivas de retención

Puede aplicar etiquetas de retención automáticas solo a los archivos de vídeo de grabación de reuniones de Teams a través de la propiedad ProgID. Para más información, consulte [Cómo aplicar automáticamente una etiqueta de retención a las grabaciones de reuniones de Teams](/microsoft-365/compliance/apply-retention-labels-automatically?view=o365-worldwide#microsoft-teams-meeting-recordings).

### <a name="data-loss-prevention-dlp-policies"></a>Directivas para la prevención de pérdida de datos (DLP)

También puede aplicar directivas DLP a archivos de grabación de reuniones mediante la propiedad ProgID. En la regla DLP para archivos en SharePoint Online y OneDrive para la Empresa, establezca las condiciones de la siguiente manera:

- Propiedad del documento = *ProgID*
- Valor = *Media.Meeting*

Para más información sobre DLP, consulte el artículo [Información sobre la prevención de pérdida de datos](/microsoft-365/compliance/dlp-learn-about-dlp)

## <a name="related-topics"></a>Temas relacionados

- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
