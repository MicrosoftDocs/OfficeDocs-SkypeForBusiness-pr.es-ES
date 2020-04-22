---
title: Grabación de reuniones en la nube de Teams
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: nakulm
search.appverid: MET150
f1.keywords:
- NOCSH
description: Cómo activar y administrar la grabación de reuniones en Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1098b1e316bb6ed747577183fc144bf2db7d0b9d
ms.sourcegitcommit: 48f64fa38509cf7141b944cd3da60409ec51860b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43751857"
---
# <a name="teams-cloud-meeting-recording"></a>Grabación de reuniones en la nube de Teams

En Microsoft Teams, los usuarios pueden grabar sus reuniones y llamadas de grupo de Teams para capturar el audio, el vídeo y la actividad de pantalla compartida. También hay una opción para que las grabaciones tengan una transcripción automática, para que los usuarios puedan reproducir grabaciones de reunión con subtítulos y buscar elementos de discusión importantes en la transcripción. La grabación se realiza en la nube y se guarda en [Microsoft Stream](https://docs.microsoft.com/stream/), para que los usuarios puedan compartirla de forma segura en su organización.

Relacionado: [Documentación de usuario final de grabación de reuniones de Teams](https://aka.ms/recordmeeting)

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Requisitos previos para grabación de reuniones en la nube de Teams

Para que se graben las reuniones de un usuario de Teams debe estar habilitarse Microsoft Stream para el espacio empresarial. Además, son necesarios los siguientes requisitos previos tanto para el organizador de la reunión como para la persona que inicia la grabación:

- El usuario tiene Office 365 E1, E3, E5, a1, a3, A5, M365 Empresa, Empresa Premium o Empresa Essentials
- El usuario debe tener una licencia para Microsoft Stream<sup>1</sup> 
- El usuario tiene permisos de carga de vídeo para Microsoft Stream
- El usuario ha dado su consentimiento a las directrices de la empresa, si han sido configuradas por el administrador
- El usuario tiene suficiente espacio de almacenamiento en Microsoft Stream para guardar las grabaciones
- El usuario tiene el parámetro TeamsMeetingPolicy-AllowCloudRecording definido como true
- El usuario no es un usuario anónimo, Invitado o federado en la reunión

> [!NOTE]
> Además, para permitir que la persona que inicia la grabación elija si la grabación se transcribe automáticamente, la opción TeamsMeetingPolicy -AllowTranscription del usuario debe establecerse en true.

<sup>1</sup>El usuario debe disponer de una licencia para cargar y descargar reuniones en Microsoft Stream, pero no se necesita la licencia para grabar una reunión. Si no desea que un usuario pueda grabar una Reunión de Microsoft Teams, debe otorgar una TeamsMeetingPolicy que tenga la opción AllowCloudRecording establecida en $False.

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>Configurar la grabación de reuniones en la nube de Teams para los usuarios de su organización

En esta sección se explica cómo puede configurar y planear la grabación de reuniones de Teams.

### <a name="turn-on-microsoft-stream-for-users-in-the-organization"></a>Activar Microsoft Stream para los usuarios de la organización

Microsoft Stream está disponible como parte de las suscripciones de Office 365 válidas o como un servicio independiente.  Para obtener más información, consulte [Información general sobre licencias de Stream](https://docs.microsoft.com/stream/license-overview)  Microsoft Stream está ahora incluido en Microsoft 365 Empresa, Office 365 Empresa Premium y Office 365 Empresa Essentials.

Obtenga más información sobre cómo [asignar licencias a los usuarios en Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) de modo que los usuarios puedan tener acceso a Microsoft Stream. Asegúrese de que Microsoft Stream no esté bloqueado para los usuarios, como se define en [este artículo](https://docs.microsoft.com/stream/disable-user-organization).

### <a name="make-sure-users-have-upload-video-permissions-in-microsoft-stream"></a>Asegurarse de que los usuarios tienen permisos de carga de vídeo en Microsoft Stream

De forma predeterminada, todos los usuarios de la empresa pueden crear contenido en Stream, una vez que Stream esté habilitado y la licencia esté asignada al usuario. Un administrador de Microsoft Stream puede [restringir que los empleados puedan crear contenido](https://docs.microsoft.com/stream/restrict-uploaders) en Stream. Los usuarios que estén en esta lista restringida no podrán grabar reuniones.

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>Notifique a los empleados que deben dar su consentimiento a las directrices de la empresa en Microsoft Stream

Si un administrador de Microsoft Stream ha [configurado una directiva de directrices de la empresa](https://docs.microsoft.com/stream/company-policy-and-consent) y necesita que los empleados den su consentimiento a esta directiva antes de guardar contenido, los usuarios deben hacerlo antes de grabar en Microsoft Teams. Antes de implementar la característica de grabación en la organización, asegúrese de que los usuarios hayan dado su consentimiento a la directiva.

### <a name="turn-on-or-turn-off-cloud-recording"></a>Activar o desactivar la grabación en la nube

Puede usar el centro de administración de Microsoft Teams o PowerShell para establecer una directiva de reunión de Teams para controlar si se pueden grabar las reuniones del usuario.

En el centro de administración de Microsoft Teams, active o desactive la opción **Permitir la grabación en la nube** en la directiva de reunión. Para obtener más información, consulte [Administrar directivas de reunión en Teams](meeting-policies-in-teams.md#allow-cloud-recording).

Con PowerShell, configure la opción AllowCloudRecording en TeamsMeetingPolicy. Para obtener más información, consulte [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) y [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

Tenga en cuenta que tanto el organizador de la reunión como el iniciador la grabación necesitan tener permisos de grabación para grabar la reunión. A menos que haya asignado una directiva personalizada a los usuarios, los usuarios recibirán la directiva global, que tiene AllowCloudRecording deshabilitada de forma predeterminada.

Para que un usuario revierta a la directiva global, use el siguiente cmdlet para quitar una asignación de directiva específica para un usuario:

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

Para cambiar el valor de AllowCloudRecording en la directiva global, use el siguiente cmdlet:

`Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $false`
</br>
</br>


|                                                                 Escenario                                                                 |                                                                                                                                                                         Pasos                                                                                                                                                                          |
|------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                    Quiero que todos los usuarios de mi empresa puedan grabar sus reuniones                                    |                                                                     <ol><li>Confirmar que CsTeamsMeetingPolicy global tiene AllowCloudRecording = True<li>Todos los usuarios tienen CsTeamsMeetingPolicy global o una de las directivas de CsTeamsMeetingPolicy con AllowCloudRecording = True </ol>                                                                     |
| Quiero que la mayoría de los usuarios puedan grabar sus reuniones, pero deshabilitar de forma selectiva usuarios específicos a los que no se les permite grabar |        <ol><li>Confirmar que CsTeamsMeetingPolicy global tiene AllowCloudRecording = True<li>La mayoría de los usuarios tienen CsTeamsMeetingPolicy global o una de las directivas de CsTeamsMeetingPolicy con AllowCloudRecording = True<li>A los demás usuarios se les ha otorgado una de las directivas CsTeamsMeetingPolicy con AllowCloudRecording = False</ol>         |
|                                                   Quiero deshabilitar la grabación al 100%                                                    |                                                                <ol><li>Confirmar que CsTeamsMeetingPolicy global tiene AllowCloudRecording = False<li>A todos los usuarios se les ha otorgado la CsTeamsMeetingPolicy global o una de las directivas de CsTeamsMeetingPolicy con AllowCloudRecording = False                                                                 |
|      Quiero que la grabación esté desactivada para la mayoría de los usuarios, pero permite de forma selectiva que se permita a determinados usuarios grabar       | <ol><li>Confirmar que CsTeamsMeetingPolicy global tiene AllowCloudRecording = False<li>A la mayoría de los usuarios se les ha otorgado la CsTeamsMeetingPolicy global o una de las directivas de CsTeamsMeetingPolicy con AllowCloudRecording = False<li>Todos los usuarios tienen CsTeamsMeetingPolicy global o una de las directivas de CsTeamsMeetingPolicy con AllowCloudRecording = True <ol> |
|                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                  |
#### <a name="where-your-meeting-recordings-are-stored"></a>Dónde se almacenan las grabaciones de reuniones

Las grabaciones de reuniones se almacenan en el almacenamiento en la nube de Microsoft Stream. Una vez que grabe una reunión, Microsoft Stream la conservará para siempre (o hasta que el propietario de la grabación la elimine). Si la grabación no se carga en la secuencia, se almacena en el almacenamiento en la nube de Teams, que está disponible para su descarga durante 20 días. Actualmente, la característica de grabación de reuniones está desactivada para los clientes cuyos datos se almacenan en el país incluso si Microsoft Stream no está disponible en la región de residencia de datos del país en la que se almacenan los datos.

Para buscar la región donde se almacenan los datos de Microsoft Stream, en Microsoft Stream, haga clic en **?** en la esquina superior derecha, haga clic en **Acerca de Microsoft Stream** y, después, haga clic en **Los datos se almacenan en**.  Para obtener más información sobre las regiones donde Microsoft Stream almacena datos, consulte [Preguntas frecuentes sobre Microsoft Stream](https://docs.microsoft.com/stream/faq#which-regions-does-microsoft-stream-host-my-data-in).

Para obtener más información sobre dónde se almacenan los datos en los servicios de Office 365, consulte [¿Dónde se encuentran los datos?](https://products.office.com/where-is-your-data-located?rtc=1)

### <a name="turn-on-or-turn-off-recording-transcription"></a>Activar o desactivar la transcripción de grabaciones

Cuando los usuarios graban sus reuniones de Teams, pueden confirmar si se debe generar automáticamente una transcripción una vez grabada la reunión. Si ha deshabilitado la función de transcripción para el organizador de la reunión y el iniciador de la grabación, el iniciador de la grabación no tendrá la opción de transcribir las grabaciones de las reuniones.

Puede usar el centro de administración de Microsoft Teams o PowerShell para establecer una directiva de reunión de Teams para controlar si el iniciador de la reunión tiene la opción de transcribir la grabación de la reunión.

En el centro de administración de Microsoft Teams, active o desactive la opción **Permitir transcripción** en la directiva de reunión. Para obtener más información, consulte [Administrar directivas de reunión en Teams](meeting-policies-in-teams.md#allow-transcription).

Con PowerShell, configure la opción AllowTranscription en TeamsMeetingPolicy. Para obtener más información, consulte [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) y [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

A menos que haya asignado una directiva personalizada a los usuarios, los usuarios recibirán la directiva global, que tiene AllowTranscription deshabilitada de forma predeterminada.

Para que un usuario revierta a la directiva global, use el siguiente cmdlet para quitar una asignación de directiva específica para un usuario:

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

Para cambiar el valor de AllowCloudRecording en la directiva global, use el siguiente cmdlet:

`Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $false`
</br>
</br>

|Escenario|Pasos |
|---|---|
|Quiero que todos los usuarios de mi empresa puedan transcribir cuando inician la grabación de una reunión |<ol><li>Confirmar que CsTeamsMeetingPolicy global tiene AllowTranscription = True <li>Todos los usuarios tienen csTeamsMeetingPolicy global o una de las directivas de CsTeamsMeetingPolicy con AllowTranscription = True </ol>|
|Quiero que la mayoría de los usuarios puedan transcribir las grabaciones de las reuniones, pero deshabilitar de forma selectiva usuarios específicos a los que no se les permite transcribir |<ol><li>Confirmar que CsTeamsMeetingPolicy global tiene AllowTranscription = True <li>La mayoría de los usuarios tienen CsTeamsMeetingPolicy global o una de las directivas de CsTeamsMeetingPolicy con AllowTranscription = True <li>A los demás usuarios se les ha otorgado una de las directivas de CsTeamsMeetingPolicy con AllowTranscription = False </ol>|
|Quiero que la transcripción de la grabación se deshabilite al 100% |<ol><li>Confirmar que CsTeamsMeetingPolicy global tiene AllowTranscription = False <li>A todos los usuarios se les ha otorgado la CsTeamsMeetingPolicy global o una de las directivas de CsTeamsMeetingPolicy con AllowTranscription = False </ol>|
|Quiero que la transcripción esté deshabilitada para la mayoría de los usuarios, pero permitir de forma selectiva que determinados usuarios puedan transcribir |<ol><li>Confirmar que CsTeamsMeetingPolicy global tiene AllowCloudRecording = False <li>A la mayoría de los usuarios se les ha otorgado la CsTeamsMeetingPolicy global o una de las directivas de CsTeamsMeetingPolicy con AllowCloudRecording = False <li>Todos los usuarios tienen CsTeamsMeetingPolicy global o una de las directivas de CsTeamsMeetingPolicy con AllowCloudRecording = True </ol>|
|||

### <a name="planning-for-storage"></a>Planificación de almacenamiento

El tamaño de una grabación de 1 hora es de 400 MB. Asegúrese de entender la capacidad necesaria para los archivos grabados y de disponer de suficiente espacio de almacenamiento en Microsoft Stream.  Lea [este artículo](https://docs.microsoft.com/stream/license-overview) para obtener información sobre el almacenamiento básico incluido en la suscripción y cómo comprar almacenamiento adicional.

## <a name="manage-meeting-recordings"></a>Administrar grabaciones de reuniones

Las grabaciones de reuniones se consideran contenidos propiedad del espacio empresarial. Si el propietario de la grabación abandona la empresa, el administrador puede abrir la URL del vídeo de la grabación en Microsoft Stream en modo de administrador. El administrador puede eliminar la grabación, actualizar cualquier metadato de la grabación o cambiar los permisos para el vídeo de la grabación. Obtenga más información sobre [las funciones de administración en Stream](https://docs.microsoft.com/stream/manage-content-permissions).

> [!NOTE]
> Para obtener más información sobre cómo administrar grabaciones y acceso de usuarios, consulte [Administrar datos de usuario en Microsoft Stream](https://docs.microsoft.com/stream/managing-user-data) y [Permisos y privacidad en Microsoft Stream](https://docs.microsoft.com/stream/portal-permissions).


## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>Cumplimiento y eDiscovery para grabaciones de reuniones

Las grabaciones de reuniones se almacenan en Microsoft Stream, que es compatible con Office 365 nivel C. El mensaje de grabación completa se encuentra disponible en la función de búsqueda de contenido de cumplimiento de Microsoft Teams para admitir las solicitudes de e-Discovery para administradores de cumplimiento que estén interesados en las grabaciones de reuniones o llamadas de Microsoft Streams. Los administradores de cumplimiento pueden buscar la palabra clave "grabación" en la línea de asunto del elemento en la vista previa de búsqueda de contenido de cumplimiento y detectar grabaciones de reuniones y llamadas en la organización. Un requisito previo para que vean todas las grabaciones es que deberán tener acceso de administrador en Microsoft Stream. Obtenga más información sobre [asignar permisos de administrador en Stream](https://docs.microsoft.com/stream/assign-administrator-user-role).

## <a name="related-topics"></a>Temas relacionados

- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
