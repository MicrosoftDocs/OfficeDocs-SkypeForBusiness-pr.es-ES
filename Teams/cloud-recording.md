---
title: Grabación de reuniones en la nube de Teams
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
ms.reviewer: sonua
search.appverid: MET150
description: Guía práctica para implementar características de voz en la nube en Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9feaffd1677d96c53dee57b03f9061c6fa8184ce
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516946"
---
# <a name="teams-cloud-meeting-recording"></a>Grabación de reuniones en la nube de Teams

En Microsoft Teams, los usuarios pueden registrar sus reuniones de Teams y las llamadas de grupo para capturar la actividad de audio, vídeo y pantalla compartida. También hay una opción para que las grabaciones tengan una transcripción automática, para que los usuarios puedan reproducir grabaciones de reunión con subtítulos y buscar elementos de discusión importantes en la transcripción. La grabación se produce en la nube y se guarda en [Microsoft Stream](https://docs.microsoft.com/stream/)para que los usuarios puedan compartirla de forma segura en toda la organización.

Relacionado: [documentación de usuario final del registro de reuniones de Teams](https://aka.ms/recordmeeting)

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Requisitos previos para la grabación de reuniones en la nube de Teams

Para que se graben las reuniones de los usuarios de un equipo, Microsoft Stream debe estar habilitado para el inquilino. Además, los siguientes requisitos previos son necesarios tanto para el organizador de la reunión como para la persona que inicia la grabación:

- El usuario tiene un Office 365 E1, E3, E5, a1, a3, A5, M365 Business, Business Premium o Business Essentials
- El usuario debe tener una licencia para Microsoft Stream<sup>1</sup> 
- El usuario tiene permisos de vídeo de carga de Microsoft Stream
- El usuario ha reenviado a las pautas de la empresa, si el administrador la configuró
- El usuario tiene suficiente espacio de almacenamiento en Microsoft Stream para que se guarden las grabaciones
- El usuario tiene la opción de TeamsMeetingPolicy-AllowCloudRecording establecida en true
- El usuario no es un usuario anónimo, invitado o federado en la reunión

> [!NOTE]
> Además, para permitir que la persona que inicia la grabación elija si desea transcribir automáticamente la grabación, la configuración de TeamsMeetingPolicy-AllowTranscription del usuario debe establecerse en true

<sup>1</sup> El usuario debe tener licencia para cargar o descargar reuniones a o desde Microsoft Stream; sin embargo, no necesitan la licencia para grabar una reunión. Si desea bloquear a un usuario para que no grabe una reunión de Microsoft Teams, debe conceder un TeamsMeetingPolicy que tenga AllowCloudRecording establecido en $False.

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>Configurar la grabación de reuniones en la nube de Teams para los usuarios de su organización

En esta sección se explica cómo configurar y planear la grabación de reuniones de Teams.

### <a name="enable-microsoft-stream-for-users-in-the-organization"></a>Habilitar Microsoft Stream para los usuarios de la organización

Microsoft Stream está disponible como parte de suscripciones de Office 365 válidas o como un servicio independiente.  Para obtener más información, vea la [información general sobre licencias de transmisión](https://docs.microsoft.com/stream/license-overview) .  Microsoft Stream está ahora incluido en Microsoft 365 Business, Office 365 Business Premium y Office 365 Business Essentials.

Obtenga más información sobre cómo puede [asignar licencias a usuarios en Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) para que los usuarios puedan tener acceso a Microsoft Stream. Asegúrese de que Microsoft Stream no está bloqueado para los usuarios, tal y como se define en [este artículo](https://docs.microsoft.com/stream/disable-user-organization).

### <a name="ensure-that-users-have-upload-video-permissions-in-microsoft-stream"></a>Asegurarse de que los usuarios tienen permisos de carga de vídeo en Microsoft Stream

De forma predeterminada, todas las personas de la compañía pueden crear contenido en la secuencia, una vez que la secuencia está habilitada y la licencia se asigna al usuario. Un administrador de Microsoft Stream puede [restringir los empleados para la creación de contenido](https://docs.microsoft.com/stream/restrict-uploaders) en Stream. Los usuarios que se encuentren en esta lista restringida no podrán grabar reuniones.

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>Notificar a los empleados el consentimiento de las directrices de la empresa en Microsoft Stream

Si un administrador de Microsoft Stream ha [configurado la Directiva de directrices](https://docs.microsoft.com/stream/company-policy-and-consent) de la empresa y requiere que los empleados acepten esta Directiva antes de guardar el contenido, los usuarios deben hacerlo antes de grabar en Microsoft Teams. Antes de implementar la característica de grabación en la organización, asegúrese de que los usuarios hayan reenviado a la Directiva.

### <a name="turn-on-or-turn-off-cloud-recording"></a>Activar o desactivar la grabación en la nube

Use la configuración AllowCloudRecording en TeamsMeetingPolicy en Teams PowerShell para controlar si las reuniones de un usuario se pueden grabar o no. Puede obtener más información sobre cómo administrar TeamsMeetingPolicy con Office 365 PowerShell [aquí](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Tenga en cuenta que tanto el organizador de la reunión como el iniciador de la grabación necesitan tener los permisos de grabación para grabar la reunión. A menos que haya asignado una directiva personalizada a los usuarios, los usuarios obtienen la directiva global, que tiene AllowTranscription deshabilitada de forma predeterminada.

Para que un usuario vuelva a la directiva global, use el siguiente cmdlet para quitar una asignación de directiva específica para un usuario:

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

Para cambiar el valor de AllowCloudRecording en una directiva global, use el siguiente cmdlet:

`Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $false`
</br>
</br>


|                                                                 Escenario                                                                 |                                                                                                                                                                         Pasos                                                                                                                                                                          |
|------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                    Quiero que todos los usuarios de mi empresa puedan grabar sus reuniones                                    |                                                                     <ol><li>Confirmar que el CsTeamsMeetingPolicy global tiene AllowCloudRecording = true<li>Todos los usuarios tienen el CsTeamsMeetingPolicy global o una de las directivas de CsTeamsMeetingPolicy con AllowCloudRecording = true </ol>                                                                     |
| Quiero que la mayoría de mis usuarios puedan grabar sus reuniones, pero deshabilitar de forma selectiva a determinados usuarios que no tienen permiso para grabar |        <ol><li>Confirmar GlobalCsTeamsMeetingPolicy tiene AllowCloudRecording = true<li>La mayoría de los usuarios tienen el CsTeamsMeetingPolicy global o una de las directivas de CsTeamsMeetingPolicy con AllowCloudRecording = true<li>A todos los demás usuarios se les ha concedido una de las directivas de CsTeamsMeetingPolicy con AllowCloudRecording = false</ol>         |
|                                                   Quiero que la grabación sea 100% deshabilitada                                                   |                                                                <ol><li>Confirmar que el CsTeamsMeetingPolicy global tiene AllowCloudRecording = false<li>A todos los usuarios se les ha concedido la CsTeamsMeetingPolicy global o una de las directivas de CsTeamsMeetingPolicy con AllowCloudRecording = false                                                                 |
|      Quiero que la grabación esté deshabilitada para la mayoría de los usuarios, pero permite de forma selectiva que usuarios específicos puedan grabar       | <ol><li>Confirmar que el CsTeamsMeetingPolicy global tiene AllowCloudRecording = false<li>A la mayoría de los usuarios se les ha concedido la CsTeamsMeetingPolicy global o una de las directivas de CsTeamsMeetingPolicy con AllowCloudRecording = false<li>A todos los demás usuarios se les ha concedido una de las directivas de CsTeamsMeetingPolicy con AllowCloudRecording = true <ol> |
|                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                        |

### <a name="turn-on-or-turn-off-recording-transcription"></a>Activar o desactivar la transcripción de la grabación

Cuando los usuarios registran sus reuniones de Teams, pueden confirmar si se debe generar automáticamente una transcripción después de que se grabe la reunión. Si los administradores han deshabilitado la función de transcripción para el organizador de la reunión y el iniciador de la grabación, el iniciador de grabación no tendrá la opción de transcribir las grabaciones de la reunión.

Use la configuración AllowTranscription en TeamsMeetingPolicy en Teams PowerShell para controlar si un iniciador de grabaciones tiene una opción para transcribir la grabación de la reunión. Puede obtener más información sobre cómo administrar TeamsMeetingPolicy con Office 365 PowerShell [aquí](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

A menos que haya asignado una directiva personalizada a los usuarios, obtendrán una directiva global, que tiene AllowTranscription deshabilitado de forma predeterminada.

Para que un usuario vuelva a la directiva global, use el siguiente cmdlet para quitar una asignación de directiva específica para un usuario:

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

Para cambiar el valor de AllowCloudRecording en una directiva global, use el siguiente cmdlet:

`Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $false`
</br>
</br>

|Escenario|Pasos |
|---|---|
|Deseo que todos los usuarios de mi compañía puedan transcribir al iniciar la grabación de una reunión |<ol><li>Confirmar que el CsTeamsMeetingPolicy global tiene AllowTranscription = true <li>Todos los usuarios tienen el csTeamsMeetingPolicy global o una de las directivas de CsTeamsMeetingPolicy con AllowTranscription = true. </ol>|
|Quiero que la mayoría de los usuarios puedan transcribir las grabaciones de la reunión, pero deshabilitar de forma selectiva a determinados usuarios que no tienen permitido transcribir |<ol><li>Confirmar que el CsTeamsMeetingPolicy global tiene AllowTranscription = true <li>La mayoría de los usuarios tienen el CsTeamsMeetingPolicy global o una de las directivas de CsTeamsMeetingPolicy con AllowTranscription = true <li>A todos los demás usuarios se les ha concedido una de las directivas de CsTeamsMeetingPolicy con AllowTranscription = false </ol>|
|Deseo que la transcripción de la grabación esté deshabilitada en 100% |<ol><li>Confirmar que el CsTeamsMeetingPolicy global tiene AllowTranscription = false <li>A todos los usuarios se les ha concedido la CsTeamsMeetingPolicy global o una de las directivas de CsTeamsMeetingPolicy con AllowTranscription = false </ol>|
|Deseo que la transcripción esté deshabilitada para la mayoría de los usuarios, pero habilite selectivamente usuarios específicos a los que se les permite transcribir |<ol><li>Confirmar que el CsTeamsMeetingPolicy global tiene AllowCloudRecording = false <li>A la mayoría de los usuarios se les ha concedido la CsTeamsMeetingPolicy global o una de las directivas de CsTeamsMeetingPolicy con AllowCloudRecording = false <li>A todos los demás usuarios se les ha concedido una de las directivas de CsTeamsMeetingPolicy con AllowCloudRecording = true </ol>|
|||

### <a name="planning-for-storage"></a>Planificación de almacenamiento

El tamaño de una grabación de 1 hora es de 400 MB. Asegúrese de comprender la capacidad necesaria para los archivos grabados y de disponer de suficiente espacio de almacenamiento disponible en Microsoft Stream.  Lea [este artículo](https://docs.microsoft.com/stream/license-overview) para comprender el almacenamiento básico que se incluye en la suscripción y cómo comprar almacenamiento adicional.

## <a name="manage-meeting-recordings"></a>Administrar las grabaciones de la reunión
Las grabaciones de la reunión se consideran contenido de propiedad del inquilino. Si el propietario de la grabación abandona la empresa, el administrador puede abrir la dirección URL de grabación de video en Microsoft stream en modo de administración. El administrador puede eliminar la grabación, actualizar cualquier metadato de grabación o cambiar los permisos para el vídeo de grabación. Obtenga más información sobre las [capacidades de administración en Stream](https://docs.microsoft.com/stream/manage-content-permissions).

## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>Cumplimiento y eDiscovery para las grabaciones de reuniones
Las grabaciones de la reunión se almacenan en Microsoft Stream, que es compatible con Office 365 Tier-C. Para admitir solicitudes de descubrimiento electrónico para administradores de cumplimiento interesados en las grabaciones de reuniones o llamadas para Microsoft streams, el mensaje de grabación completada está disponible en la funcionalidad de búsqueda de contenido de cumplimiento de Microsoft Teams. Los administradores de cumplimiento pueden buscar la palabra clave "grabación" en la línea de asunto del elemento en la vista previa de búsqueda del contenido de cumplimiento y descubrir las grabaciones de las reuniones y las llamadas en la organización. Un requisito previo para poder ver todas las grabaciones es que deben configurarse en Microsoft Stream con acceso de administrador. Obtenga más información sobre cómo [asignar permisos de administrador en la secuencia](https://docs.microsoft.com/stream/assign-administrator-user-role).

## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad en lugar de usar únicamente el centro de administración de Microsoft 365, por ejemplo, cuando está realizando cambios de configuración para muchos usuarios a la vez. To get started with Windows PowerShell, see these topics:

- [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
- [Configurar el equipo para Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525038)

