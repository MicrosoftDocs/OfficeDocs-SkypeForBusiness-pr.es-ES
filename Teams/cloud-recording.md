---
title: Grabación de la reunión de los equipos en la nube
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
description: Guía práctica para implementar características de voz en la nube en Microsoft Teams.
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5ae144405375daa818f334fdf5be85e75cd4f6b1
ms.sourcegitcommit: bb3f235265cddae9578ec1bf605c4edc7f14fb30
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "25851587"
---
# <a name="teams-cloud-meeting-recording"></a>Grabación de la reunión de los equipos en la nube

> [!Note]
> [!INCLUDE [preview-feature](includes/preview-feature.md)]

En Microsoft Teams, los usuarios pueden registrar sus reuniones de los equipos y las llamadas de grupo para capturar audio, vídeo y uso compartido de actividad de pantalla. También es una opción para grabaciones tener transcripción automática, por lo que los usuarios pueden reproducir grabaciones de la reunión con títulos cerrados y buscar elementos de discusión importantes en la transcripción. La grabación sucede en la nube y se guarda en la [Secuencia de Microsoft](https://docs.microsoft.com/stream/), por lo que los usuarios pueden compartirla de manera segura en toda su organización.

[Grabación de documentación del usuario final de reunión de los equipos](https://aka.ms/recordmeeting) de relacionados:

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Requisitos previos para la grabación de la reunión de los equipos en la nube

Para que reuniones del usuario de los equipos que se registre, Microsoft Stream debe estar habilitada para el inquilino. Además, los siguientes requisitos previos son necesarios para el organizador de la reunión y la persona que está iniciando la grabación:

- El usuario tiene un Office 365 E1, E3, E5, A1, A3, A5, M365 Business, Business Premium o Business Essentials
- El usuario debe tener licencia para Microsoft Stream
- El usuario tiene Microsoft Stream cargar permisos de vídeo
- Usuario ha aceptado a las directrices de la compañía, si establecido por el administrador
- El usuario tiene suficiente espacio de almacenamiento en Microsoft Stream para grabaciones que se guarde
- El usuario tiene TeamsMeetingPolicy AllowCloudRecording configuración establecida en true
- El usuario tiene TeamsMeetingPolicy AllowTranscription configuración establecida en true, por lo que el usuario puede elegir si desea transcribir automáticamente las grabaciones
- Usuario no es un anónimo, invitado o usuario federado en la reunión

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>Configurar la grabación de la reunión los equipos en la nube para los usuarios de su organización

En esta sección se explica cómo puede configurar y planeación para grabar las reuniones de los equipos.

### <a name="enable-microsoft-stream-for-users-in-the-organization"></a>Habilitar Microsoft Stream para los usuarios de la organización

Microsoft Stream está disponible como parte de suscripciones a Office 365 optan o como un servicio independiente.  Vea la [información general sobre licencias de secuencia](https://docs.microsoft.com/stream/license-overview) para obtener más detalles.  Tenga en cuenta que Microsoft Stream no se incluye en Business Essentials o planes de Business Premium.

Obtenga más información acerca de cómo se pueden [asignar licencias a los usuarios de Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) para que los usuarios pueden tener acceso a Microsoft Stream. Asegúrese de que Microsoft Stream no está bloqueado para los usuarios, como se define en [este artículo](https://docs.microsoft.com/stream/disable-user-organization).

### <a name="ensure-that-users-have-upload-video-permissions-in-microsoft-stream"></a>Asegúrese de que los usuarios han cargar permisos de vídeo en Microsoft Stream

De forma predeterminada, todas las personas de la empresa pueden crear contenido en secuencia, una vez que la secuencia está habilitada y la licencia está asignada al usuario. Un administrador de Microsoft Stream puede [restringir los empleados para la creación de contenido](https://docs.microsoft.com/stream/restrict-uploaders) en la secuencia. Los usuarios que se encuentran en esta lista restringida no podrá grabar las reuniones.

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>Notificar a los empleados a da su consentimiento a las directrices de la empresa en Microsoft Stream

Si un administrador de Microsoft Stream tiene que [Configurar la directiva de empresa directriz](https://docs.microsoft.com/stream/company-policy-and-consent) y requiere que los empleados Aceptar esta directiva antes de guardar el contenido, los usuarios deben hacerlo antes de la grabación en Microsoft Teams. Antes de desplegar la característica de grabación de la organización, asegúrese de que han dado su consentimiento de los usuarios a la directiva.

### <a name="enabledisable-cloud-recording-for-users"></a>Habilitar o deshabilitar la grabación para los usuarios de nube

Use la opción AllowCloudRecording en TeamsMeetingPolicy en los equipos de PowerShell para controlar si se permiten las reuniones de un usuario que se registre o no. Encontrará más información acerca de cómo administrar TeamsMeetingPolicy con Office 365 PowerShell [aquí](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Tenga en cuenta que el organizador de la reunión y el iniciador de grabación deben tener los permisos de grabación para grabar la reunión. A menos que haya asignado una directiva personalizada a los usuarios, los usuarios obtendrán una directiva Global, que tiene AllowTranscription deshabilitado de forma predeterminada.

Para que un usuario se retrocede a la directiva Global, use el siguiente cmdlet para quitar una asignación de directiva específica de un usuario:

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

Para cambiar el valor de AllowCloudRecording en la directiva Global, use el siguiente cmdlet:

`Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $false`
</br>
</br>


|                                                                 Escenario                                                                 |                                                                                                                                                                         Pasos                                                                                                                                                                          |
|------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                    Deseo que todos los usuarios de mi compañía para poder registrar sus reuniones                                    |                                                                     <ol><li>Confirmar CsTeamsMeetingPolicy Global tiene AllowCloudRecording = True<li>Todos los usuarios tengan el Global OR CsTeamsMeetingPolicy una de las directivas de CsTeamsMeetingPolicy con AllowCloudRecording = True </ol>                                                                     |
| Deseo que la mayoría de Mis usuarios puedan registrar sus reuniones pero deshabilitar selectivamente los usuarios específicos que no se permiten para registrar |        <ol><li>Confirmar GlobalCsTeamsMeetingPolicy tiene AllowCloudRecording = True<li>La mayoría de los usuarios tienen la Global CsTeamsMeetingPolicy o una de las directivas de CsTeamsMeetingPolicy con AllowCloudRecording = True<li>Se han concedido todos los demás usuarios una de las directivas de CsTeamsMeetingPolicy con AllowCloudRecording = False</ol>         |
|                                                   La opción I want grabación para que sea 100% deshabilitado                                                   |                                                                <ol><li>Confirmar CsTeamsMeetingPolicy Global tiene AllowCloudRecording = False<li>Todos los usuarios se han concedido OR CsTeamsMeetingPolicy Global una de las directivas de CsTeamsMeetingPolicy con AllowCloudRecording = False                                                                 |
|      La opción I want grabación para ser deshabilitado para la mayoría de los usuarios sin habilitar de forma selectiva los usuarios específicos que se permiten para registrar       | <ol><li>Confirmar CsTeamsMeetingPolicy Global tiene AllowCloudRecording = False<li>La mayoría de los usuarios se han concedido el Global CsTeamsMeetingPolicy o una de las directivas de CsTeamsMeetingPolicy con AllowCloudRecording = False<li>Se han concedido todos los demás usuarios una de las directivas de CsTeamsMeetingPolicy con AllowCloudRecording = True <ol> |
|                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                        |

### <a name="enabledisable-recording-transcription-for-users"></a>Habilitar o deshabilitar transcripción de grabación para los usuarios

Cuando los usuarios grabar sus reuniones de los equipos, puede confirmar si se debe generar automáticamente una transcripción después de la reunión se registra. Si los administradores han deshabilitado la capacidad de transcripción para el organizador de la reunión y el iniciador de grabación, el iniciador de grabación no obtendrá una opción para transcribir las grabaciones de reunión.

Use la opción AllowTranscription en TeamsMeetingPolicy en los equipos de PowerShell para controlar si un iniciador de grabación Obtiene una opción para transcribir la grabación de la reunión. Encontrará más información acerca de cómo administrar TeamsMeetingPolicy con Office 365 PowerShell [aquí](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

A menos que haya asignado una directiva personalizada a los usuarios, reciben la directiva Global, que se ha deshabilitado habilitada de forma predeterminada.

Para que un usuario se retrocede a la directiva Global, use el siguiente cmdlet para quitar una asignación de directiva específica de un usuario:

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

Para cambiar el valor de AllowCloudRecording en la directiva Global, use el siguiente cmdlet:

`Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $false`
</br>
</br>

|Escenario|Pasos |
|---|---|
|Deseo que todos los usuarios de mi compañía puedan transcribir al iniciar la grabación de una reunión |<ol><li>Confirmar CsTeamsMeetingPolicy Global tiene AllowTranscription = True <li>Todos los usuarios tienen la csTeamsMeetingPolicy Global o una de las directivas de CsTeamsMeetingPolicy con AllowTranscription = True. </ol>|
|Deseo que la mayoría de Mis usuarios puedan transcribir las grabaciones de reunión, pero deshabilitar selectivamente los usuarios específicos que no se permiten a transcribir |<ol><li>Confirmar CsTeamsMeetingPolicy Global tiene AllowTranscription = True <li>La mayoría de los usuarios tienen la Global CsTeamsMeetingPolicy o una de las directivas de CsTeamsMeetingPolicy con AllowTranscription = True <li>Se han concedido todos los demás usuarios una de las directivas de CsTeamsMeetingPolicy con AllowTranscription = False </ol>|
|La opción I want transcripción de la grabación para ser 100% deshabilitado |<ol><li>Confirmar CsTeamsMeetingPolicy Global tiene AllowTranscription = False <li>Todos los usuarios se han concedido OR CsTeamsMeetingPolicy Global una de las directivas de CsTeamsMeetingPolicy con AllowTranscription = False </ol>|
|La opción I want transcripción para ser deshabilitado para la mayoría de los usuarios, pero habilitar de forma selectiva los usuarios específicos que se permiten para transcribir |<ol><li>Confirmar CsTeamsMeetingPolicy Global tiene AllowCloudRecording = False <li>La mayoría de los usuarios se han concedido el Global CsTeamsMeetingPolicy o una de las directivas de CsTeamsMeetingPolicy con AllowCloudRecording = False <li>Se han concedido todos los demás usuarios una de las directivas de CsTeamsMeetingPolicy con AllowCloudRecording = True </ol>|
|||

### <a name="planning-for-storage"></a>Planificación de almacenamiento

El tamaño de una grabación de 1 hora es 400 MB. Asegúrese de comprender la capacidad necesaria para los archivos grabados y tener suficiente espacio de almacenamiento disponible en Microsoft Stream.  Lectura [en este artículo](https://docs.microsoft.com/stream/license-overview) para comprender el almacenamiento de base incluido en la suscripción y cómo adquirir almacenamiento adicional.

## <a name="manage-meeting-recordings"></a>Administrar grabaciones de la reunión
Las grabaciones de reunión se consideran contenido de inquilino. Si el propietario de la grabación deja la compañía, el administrador puede abrir la dirección URL de grabación de vídeo en Microsoft Stream en modo de administrador. El administrador puede eliminar la grabación, actualizar los metadatos de grabación o cambiar los permisos para la grabación de vídeo. Obtenga más información acerca de [las capacidades de administración en secuencia](https://docs.microsoft.com/stream/manage-content-permissions).

## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>Cumplimiento y exhibición de documentos electrónicos para grabaciones de la reunión
Las grabaciones de reunión se almacenan en Microsoft Stream, que es 365 Office niveles-C compatible. Para admitir las solicitudes de exhibición de documentos electrónicos para los administradores de cumplimiento que están interesados en grabaciones de reunión o llamada para Microsoft Streams, está disponible en la funcionalidad de búsqueda de contenido de cumplimiento de normas para Microsoft Teams el mensaje finalizado de grabación. Administradores de cumplimiento pueden buscar la palabra clave "grabar" en la línea de asunto del elemento en la vista previa de la búsqueda de contenido de cumplimiento de normas y descubrir la reunión y registros de llamada en la organización. Un requisito previo para ellos ver todas las grabaciones es que deben estar configuradas en Microsoft Stream con acceso de administrador. Obtenga más información acerca de [asignar permisos de administrador en secuencia](https://docs.microsoft.com/stream/assign-administrator-user-role).

## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad sobre solo usa el centro de administración de Office 365, como cuando se realizan cambios de configuración para muchos usuarios a la vez. To get started with Windows PowerShell, see these topics:

- [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
- [Configurar el equipo para Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525038)

