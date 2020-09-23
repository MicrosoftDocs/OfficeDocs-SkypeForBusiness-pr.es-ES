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
description: Guía práctica para implementar las características de voz en la nube de Teams para grabar reuniones de Teams y llamadas grupales para capturar la actividad de audio, vídeo y pantalla compartida.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b19cb5fe0ac89f800904bea4346cc185d9b822a8
ms.sourcegitcommit: 3db7c450d3afbc1049e1016d51016442e5764634
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203973"
---
# <a name="teams-cloud-meeting-recording"></a>Grabación de reuniones en la nube de Teams

En Microsoft Teams, los usuarios pueden grabar sus reuniones y llamadas de grupo de Teams para capturar el audio, el vídeo y la actividad de pantalla compartida. También hay una opción para que las grabaciones tengan una transcripción automática, para que los usuarios puedan reproducir grabaciones de reunión con subtítulos y buscar elementos de discusión importantes en la transcripción. La grabación se realiza en la nube y se guarda en [Microsoft Stream](https://docs.microsoft.com/stream/), para que los usuarios puedan compartirla de forma segura en su organización.

Relacionado: [Documentación de usuario final de grabación de reuniones de Teams](https://aka.ms/recordmeeting)

>[!Note]
> El cambio de usar Microsoft Stream a [OneDrive para la empresa y SharePoint para las grabaciones](tmr-meeting-recording-change.md) de la reunión será un enfoque por fases. En el lanzamiento podrá optar por esta experiencia, en noviembre tendrá que optar por no participar si desea seguir usando la secuencia y, a principios de 2021, necesitaremos todos los clientes de OneDrive para la empresa y SharePoint para las grabaciones de la reunión.

> [!NOTE]
> Para obtener información sobre el uso de roles en reuniones de Teams y sobre cómo cambiar los roles de los usuarios, vea [roles en una reunión de Teams](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Requisitos previos para grabación de reuniones en la nube de Teams

Para que se graben las reuniones de los usuarios de un equipo, Microsoft Stream debe estar habilitado para el inquilino. Además, son necesarios los siguientes requisitos previos tanto para el organizador de la reunión como para la persona que inicia la grabación:

- El usuario tiene Office 365 E1, E3, E5, a1, a3, A5, Microsoft 365 empresa Premium, Business Standard o Business Basic<sup>1</sup>
- El usuario debe tener una licencia para Microsoft Stream<sup>2</sup> 
- El usuario tiene permisos de carga de vídeo para Microsoft Stream
- El usuario ha dado su consentimiento a las directrices de la empresa, si han sido configuradas por el administrador
- El usuario tiene suficiente espacio de almacenamiento en Microsoft Stream para guardar las grabaciones
- El usuario tiene el parámetro TeamsMeetingPolicy-AllowCloudRecording definido como true
- El usuario no es un usuario anónimo, Invitado o federado en la reunión
- Para habilitar la transcripción de la reunión de un usuario, la política de reunión de Teams a la que están asignadas debe tener el valor-AllowTranscription establecido en true.

<sup>1</sup> a partir del 20 de agosto de 2020, el acceso al archivo de grabación de la reunión vencerá después de 21 días para los usuarios con a1. Para obtener más información, vea [cargar una grabación de reunión de Microsoft Teams en una secuencia](https://docs.microsoft.com/stream/portal-upload-teams-meeting-recording).

<sup>2</sup> el usuario debe tener licencia para cargar o descargar reuniones a o desde Microsoft Stream; sin embargo, no necesitan la licencia para grabar una reunión. Si no desea que un usuario pueda grabar una Reunión de Microsoft Teams, debe otorgar una TeamsMeetingPolicy que tenga la opción AllowCloudRecording establecida en $False.

> [!IMPORTANT] 
> Los usuarios no necesitarán una licencia de Microsoft Stream asignada si quiere que los usuarios solo graben y descarguen las grabaciones. Esto significa que las grabaciones no se almacenan en Microsoft Stream, sino que se almacenan en el servicio multimedia de Azure (AMS) con un límite de 21 días antes de que se elimine. En este momento, no es algo que un administrador pueda controlar o administrar, incluida la capacidad de eliminarlo.

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>Configurar la grabación de reuniones en la nube de Teams para los usuarios de su organización

En esta sección se explica cómo puede configurar y planear la grabación de reuniones de Teams.

### <a name="turn-on-microsoft-stream-for-users-in-the-organization"></a>Activar Microsoft Stream para los usuarios de la organización

Microsoft Stream está disponible como parte de las suscripciones Microsoft 365 y Office 365 y como un servicio independiente.  Para obtener más información, consulte [Información general sobre licencias de Stream](https://docs.microsoft.com/stream/license-overview)  Microsoft Stream está ahora incluido en Microsoft 365 Business, Microsoft 365 Business Standard y Microsoft 365 Business Basic.

Obtenga más información sobre cómo [asignar licencias a usuarios en microsoft 365 u Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) para que los usuarios puedan acceder a Microsoft Stream. Asegúrese de que Microsoft Stream no esté bloqueado para los usuarios, tal como se define en [bloquear la suscripción a Microsoft Stream](https://docs.microsoft.com/stream/disable-user-organization).

### <a name="make-sure-users-have-upload-video-permissions-in-microsoft-stream"></a>Asegurarse de que los usuarios tienen permisos de carga de vídeo en Microsoft Stream

De forma predeterminada, todos los usuarios de la empresa pueden crear contenido en Stream, una vez que Stream esté habilitado y la licencia esté asignada al usuario. Un administrador de Microsoft Stream puede [restringir que los empleados puedan crear contenido](https://docs.microsoft.com/stream/restrict-uploaders) en Stream. Los usuarios que estén en esta lista restringida no podrán grabar reuniones.

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>Notifique a los empleados que deben dar su consentimiento a las directrices de la empresa en Microsoft Stream

Si un administrador de Microsoft Stream ha [configurado una directiva de directrices de la empresa](https://docs.microsoft.com/stream/company-policy-and-consent) y necesita que los empleados den su consentimiento a esta directiva antes de guardar contenido, los usuarios deben hacerlo antes de grabar en Microsoft Teams. Antes de implementar la característica de grabación en la organización, asegúrese de que los usuarios hayan dado su consentimiento a la directiva.

### <a name="turn-on-or-turn-off-cloud-recording"></a>Activar o desactivar la grabación en la nube

Puede usar el centro de administración de Microsoft Teams o PowerShell para establecer una directiva de reunión de Teams para controlar si se pueden grabar las reuniones del usuario.

En el centro de administración de Microsoft Teams, active o desactive la opción **Permitir la grabación en la nube** en la directiva de reunión. Para obtener más información, consulte [Administrar directivas de reunión en Teams](meeting-policies-in-teams.md#allow-cloud-recording).

Con PowerShell, configure la opción AllowCloudRecording en TeamsMeetingPolicy. Para obtener más información, consulte [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) y [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

Tenga en cuenta que tanto el organizador de la reunión como el iniciador la grabación necesitan tener permisos de grabación para grabar la reunión. A menos que haya asignado una directiva personalizada a los usuarios, los usuarios obtienen la directiva global, que tiene AllowCloudRecording habilitado de forma predeterminada.

> [!NOTE]
> Para obtener más información sobre el uso de los roles de Teams para configurar quién tiene permiso para grabar una reunión, vea [roles de una reunión de Teams](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).

Para que un usuario revierta a la directiva global, use el siguiente cmdlet para quitar una asignación de directiva específica para un usuario:

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

Para cambiar el valor de AllowCloudRecording en la directiva global, use el siguiente cmdlet:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $false
```
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

Las grabaciones de reuniones se almacenan en el almacenamiento en la nube de Microsoft Stream. Las grabaciones se conservan y están disponibles para su visualización y descarga durante veintiún días. Actualmente, la característica de grabación de reuniones está desactivada para los clientes cuyos datos se almacenan en el país incluso si Microsoft Stream no está disponible en la región de residencia de datos del país en la que se almacenan los datos. En el futuro se activará la característica de grabación de reuniones para los clientes cuyos datos se almacenan en el país incluso si Microsoft Stream no está disponible en la región de residencia de datos del país.

Cuando este cambio se haya hecho efectivo, las grabaciones de reuniones se almacenarán de forma predeterminada en la región geográfica más cercana para Microsoft Stream. Si los datos de Teams se almacenan en el país y prefiere almacenar las grabaciones de reuniones en el país, se recomienda que desactive la característica y la active después de que se implemente Microsoft Stream en su región de residencia de datos del país. Para desactivar la característica para todos los usuarios de su organización, desactive la opción **permitir la grabación** en la nube de la Directiva de reunión global de Teams, que se encuentra en el centro de administración de Microsoft Teams.

Aquí se muestra un resumen de lo que ocurre al activar la grabación de reuniones cuando este cambio se haga efectivo:

|Si activa las grabaciones de la reunión...|Las grabaciones de reuniones se almacenan... |
|---|---|
|Antes de que Microsoft Stream esté disponible en su región de residencia de datos en el país |En la región de Microsoft Stream más cercana|
|Después de que Microsoft Stream esté disponible en su región de residencia de datos en el país |En la región de residencia de datos en el país|

En caso de los espacios empresariales nuevos y existentes que todavía no hayan activado la grabación de reuniones, las nuevas grabaciones se almacenan en el país después de que Microsoft Stream esté disponible en la región de residencia de datos del país. Sin embargo, cualquier inquilino que permita la grabación de reuniones antes de que Microsoft Stream esté disponible en la región de residencia del país seguirá usando el almacenamiento de Microsoft Stream para las grabaciones nuevas y existentes, incluso después de que Microsoft Stream esté disponible en la región de residencia de datos en el país.

Para buscar la región donde se almacenan los datos de Microsoft Stream, en Microsoft Stream, haga clic en **?** en la esquina superior derecha, haga clic en **Acerca de Microsoft Stream** y, después, haga clic en **Los datos se almacenan en**.  Para obtener más información sobre las regiones donde Microsoft Stream almacena datos, consulte [Preguntas frecuentes sobre Microsoft Stream](https://docs.microsoft.com/stream/faq#which-regions-does-microsoft-stream-host-my-data-in).

Para obtener más información sobre dónde se almacenan los datos en los servicios en Microsoft 365 u Office 365, consulte [¿dónde se encuentran los datos?](https://products.office.com/where-is-your-data-located?rtc=1)

### <a name="turn-on-or-turn-off-recording-transcription"></a>Activar o desactivar la transcripción de grabaciones

Esta configuración controla si las características de subtítulos y transcripción están disponibles durante la reproducción de grabaciones de reunión. Si desactiva esta opción, las opciones **Buscar** y **CC** no estarán disponibles durante la reproducción de una grabación de reunión. La persona que inició la grabación necesita esta configuración activada para que la grabación también incluya transcripción.

> [!NOTE]
> Actualmente, esta transcripción para reuniones grabadas solo es compatible con los usuarios que tienen el idioma de Teams establecido en inglés y cuando se habla de inglés en la reunión. Se almacenan junto con las grabaciones de la reunión en el almacenamiento en la nube de Microsoft Stream.

Puede usar el centro de administración de Microsoft Teams o PowerShell para establecer una directiva de reunión de Teams para controlar si el iniciador de la reunión tiene la opción de transcribir la grabación de la reunión.

En el centro de administración de Microsoft Teams, active o desactive la opción **Permitir transcripción** en la directiva de reunión. Para obtener más información, consulte [Administrar directivas de reunión en Teams](meeting-policies-in-teams.md#allow-transcription).

Con PowerShell, configure la opción AllowTranscription en TeamsMeetingPolicy. Para obtener más información, consulte [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) y [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

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
|Quiero que todos los usuarios de mi empresa puedan transcribir cuando inician la grabación de una reunión |<ol><li>Confirmar que CsTeamsMeetingPolicy global tiene AllowTranscription = True <li>Todos los usuarios tienen csTeamsMeetingPolicy global o una de las directivas de CsTeamsMeetingPolicy con AllowTranscription = True </ol>|
|Quiero que la mayoría de los usuarios puedan transcribir las grabaciones de las reuniones, pero deshabilitar de forma selectiva usuarios específicos a los que no se les permite transcribir |<ol><li>Confirmar que CsTeamsMeetingPolicy global tiene AllowTranscription = True <li>La mayoría de los usuarios tienen CsTeamsMeetingPolicy global o una de las directivas de CsTeamsMeetingPolicy con AllowTranscription = True <li>A los demás usuarios se les ha otorgado una de las directivas de CsTeamsMeetingPolicy con AllowTranscription = False </ol>|
|Quiero que la transcripción de la grabación se deshabilite al 100% |<ol><li>Confirmar que CsTeamsMeetingPolicy global tiene AllowTranscription = False <li>A todos los usuarios se les ha otorgado la CsTeamsMeetingPolicy global o una de las directivas de CsTeamsMeetingPolicy con AllowTranscription = False </ol>|
|Quiero que la transcripción esté deshabilitada para la mayoría de los usuarios, pero permitir de forma selectiva que determinados usuarios puedan transcribir |<ol><li>Confirmar que CsTeamsMeetingPolicy global tiene AllowCloudRecording = False <li>A la mayoría de los usuarios se les ha otorgado la CsTeamsMeetingPolicy global o una de las directivas de CsTeamsMeetingPolicy con AllowCloudRecording = False <li>Todos los usuarios tienen CsTeamsMeetingPolicy global o una de las directivas de CsTeamsMeetingPolicy con AllowCloudRecording = True </ol>|
|||

### <a name="planning-for-storage"></a>Planificación de almacenamiento

El tamaño de una grabación de 1 hora es de 400 MB. Asegúrese de entender la capacidad necesaria para los archivos grabados y de disponer de suficiente espacio de almacenamiento en Microsoft Stream.  Lea la [información general sobre licencias de Microsoft Stream](https://docs.microsoft.com/stream/license-overview) para comprender el almacenamiento básico incluido en la suscripción y cómo comprar almacenamiento adicional.

## <a name="manage-meeting-recordings"></a>Administrar grabaciones de reuniones

Las grabaciones de reuniones se consideran contenidos propiedad del espacio empresarial. Si el propietario de la grabación abandona la empresa, el administrador puede abrir la URL del vídeo de la grabación en Microsoft Stream en modo de administrador. El administrador puede eliminar la grabación, actualizar cualquier metadato de la grabación o cambiar los permisos para el vídeo de la grabación. Obtenga más información sobre [las funciones de administración en Stream](https://docs.microsoft.com/stream/manage-content-permissions).

> [!NOTE]
> Para obtener más información sobre cómo administrar grabaciones y acceso de usuarios, consulte [Administrar datos de usuario en Microsoft Stream](https://docs.microsoft.com/stream/managing-user-data) y [Permisos y privacidad en Microsoft Stream](https://docs.microsoft.com/stream/portal-permissions).

## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>Cumplimiento y eDiscovery para grabaciones de reuniones

Las grabaciones de la reunión se almacenan en Microsoft Stream, que es Microsoft 365 y Office 365 de nivel C. El mensaje de grabación completa se encuentra disponible en la función de búsqueda de contenido de cumplimiento de Microsoft Teams para admitir las solicitudes de e-Discovery para administradores de cumplimiento que estén interesados en las grabaciones de reuniones o llamadas de Microsoft Streams. Los administradores de cumplimiento pueden buscar la palabra clave "grabación" en la línea de asunto del elemento en la vista previa de búsqueda de contenido de cumplimiento y detectar grabaciones de reuniones y llamadas en la organización. Un requisito previo para que vean todas las grabaciones es que deberán tener acceso de administrador en Microsoft Stream. Obtenga más información sobre [asignar permisos de administrador en Stream](https://docs.microsoft.com/stream/assign-administrator-user-role).

## <a name="related-topics"></a>Temas relacionados

- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
