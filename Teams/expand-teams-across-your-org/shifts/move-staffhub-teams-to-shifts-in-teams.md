---
title: Mover los equipos de StaffHub a turnos
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu, gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo mover los equipos de Microsoft StaffHub y programar datos para desplazarse por Microsoft Teams.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- SPO_Content
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f449d20f4364629185f719c3217023107f774dd9
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350314"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a>Mover los equipos de Microsoft StaffHub a turnos en Microsoft Teams

> [!IMPORTANT]
> A partir del 30 de junio de 2020, Microsoft StaffHub se retirará. Estamos construyendo las capacidades de StaffHub en Microsoft Teams. En la actualidad, Teams incluye la aplicación de turnos para la administración de la programación, y las funciones adicionales se aplicarán a lo largo del tiempo. StaffHub dejará de funcionar para todos los usuarios el 30 de junio de 2020. Cualquier persona que intente abrir StaffHub recibirá un mensaje para que pueda descargar Teams. Para obtener más información, consulte [Microsoft StaffHub para que se retirará](microsoft-staffhub-to-be-retired.md).

La aplicación de turnos de Teams ofrece un enfoque simple para administrar las programaciones y el flujo constante de swaps y cancelaciones de turnos que se producen diariamente. Los miembros del equipo pueden acceder a su programación y desplazar la información directamente en la aplicación y en todos sus dispositivos para establecer sus preferencias, administrar sus programaciones y solicitar tiempo.

Este artículo le muestra cómo mover los equipos de StaffHub y programar datos para desplazarse por los equipos. Cubre lo siguiente:

- [Lo que debe saber sobre el desplazamiento a teams](#what-you-need-to-know-about-the-move-to-teams)
- [Preparar](#prepare)
- [Realizar una prueba piloto](#conduct-a-pilot) 
- [Vaya más allá de la prueba piloto y mueva todos los equipos de StaffHub](#go-beyond-your-pilot-and-move-all-staffhub-teams)
- [Supervisar el uso de Teams](#monitor-teams-usage)
- [Solución de problemas](#troubleshooting)

Tanto si es una pequeña empresa con uno o dos equipos de StaffHub como si es una empresa grande con cientos de equipos de StaffHub, aquí encontrará las instrucciones para administradores que necesita para que la transición a teams se realice correctamente.

Debe ser administrador global para poder realizar los pasos de este artículo. Si todavía no lo ha hecho, consulte las [preguntas más frecuentes sobre la jubilación de StaffHub](microsoft-staffhub-to-be-retired.md) para obtener respuestas a las preguntas que pueda tener.

## <a name="what-you-need-to-know-about-the-move-to-teams"></a>Lo que debe saber sobre el desplazamiento a teams

### <a name="when-to-move-to-teams"></a>Cuándo mover a teams

A partir del 30 de junio de 2020, se retirará StaffHub. Le recomendamos que comience a usar Teams hoy y empiece a cambiar la transición de los equipos y usuarios de su organización de StaffHub. Con la administración de programación como la característica que se usa con más frecuencia en StaffHub, le recomendamos que use la aplicación turnos en Teams en el futuro.

### <a name="what-is-moved-to-teams"></a>Qué se mueve a teams

Al mover un equipo de StaffHub, los miembros del equipo, los detalles del usuario, las programaciones del equipo y los datos del chat se mueven a teams. Los archivos no se mueven al mover un equipo de StaffHub. Si un equipo de StaffHub contiene archivos que también desea mover a Teams, mueva los archivos en un paso independiente.

Cada equipo de StaffHub necesita un grupo de Microsoft 365 o de Office 365 correspondiente. Si un equipo de StaffHub está asociado con un grupo de Microsoft 365, la configuración de privacidad del grupo se conserva cuando se mueve el equipo. Si un equipo de StaffHub no tiene un grupo de Microsoft 365 asociado, se crea automáticamente un grupo con la configuración de privacidad privada para que admita la transición.  Dada la diferencia de nomenclatura de equipo y grupo entre Teams y StaffHub, es posible que vea un nombre de equipo diferente en Teams. 

A medida que vaya migrando equipos de StaffHub a Teams, los usuarios ya no tendrán acceso a sus programaciones en StaffHub y se redirigirán a los equipos. Le recomendamos que comunique este cambio en toda la organización para minimizar las interrupciones y para animar a los usuarios a adoptar y explorar equipos. Si tiene Azure AD Premium, puede [ejecutar un informe](run-report-to-show-staffhub-usage.md) para obtener una lista de los usuarios de StaffHub de su organización que necesitan saber sobre este cambio.  

No hay ninguna opción de deshacer después de mover un equipo de StaffHub a teams.

### <a name="user-experience-when-you-move-a-team"></a>Experiencia de usuario al mover un equipo

El tiempo de inactividad es mínimo (menos de un segundo, si lo hay) para los usuarios cuando su equipo cambia de StaffHub a turnos en Teams. Los usuarios pueden seguir usando StaffHub hasta que se complete el cambio a teams. Cuando se haya completado el movimiento, los miembros del equipo verán un mensaje para informarles de que necesitan comenzar a usar turnos en Teams para acceder a su programación de equipo. Este es un ejemplo del mensaje que los usuarios ven después de que el equipo de StaffHub se mueva a teams.

![Ejemplo del mensaje que los usuarios ven.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Ejemplo del mensaje que los usuarios ven en StaffHub después de mover el equipo de StaffHub a teams")

## <a name="prepare"></a>Preparar

Aquí le mostramos cómo prepararse para desplazarse a teams.

### <a name="check-that-prerequisites-are-met"></a>Comprobar que se cumplen los requisitos previos

Antes de mover un equipo de StaffHub a Teams, asegúrese de lo siguiente:

- El usuario que ha iniciado sesión es un administrador global.
- Teams está habilitado para todos los usuarios del espacio empresarial.
- La creación de grupos de Microsoft 365 está habilitada en el inquilino.
- La teamId de StaffHub es válida.
- El equipo de StaffHub tiene al menos un propietario del equipo.
- El equipo de StaffHub contiene miembros.
- Todos los miembros del equipo StaffHub están vinculados a una cuenta de Azure AD.
- Se asigna a todos los miembros del equipo StaffHub una licencia de Teams.  

Si no se cumplen estos requisitos previos, se producirá un error en la solicitud de movimiento.

### <a name="assign-teams-licenses"></a>Asignar licencias de Teams

Cada usuario debe tener una licencia activa de Microsoft 365 o de Office 365 de [un plan apto](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) y debe tener asignada una licencia de Teams. Asignar una licencia de Teams a los usuarios les da acceso a teams.

Administra las licencias de Teams en el centro de administración de Microsoft 365. Para más información, vea [Administrar el acceso de usuarios a Teams](../../user-access.md).

> [!NOTE]
> Si su organización usa Skype empresarial y no está listo para mover a todos los usuarios a Teams, puede habilitar a Teams para sus trabajadores de los Firstline, que luego pueden ejecutar equipos junto con Skype empresarial. En este modo de coexistencia, llamadas *islas*, cada aplicación cliente funciona como una solución independiente. Para obtener más información, consulte [comprender Teams y la interoperabilidad y coexistencia de Skype empresarial](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).

### <a name="install-the-prerelease-version-of-the-staffhub-powershell-module"></a>Instalar la versión preliminar del módulo de PowerShell de StaffHub

Si todavía no lo ha hecho, [Instale la versión preliminar del módulo de PowerShell de StaffHub](install-the-staffhub-powershell-module.md).

Debe tener instalada la versión preliminar del módulo para mover los equipos de StaffHub a teams.

### <a name="link-an-azure-ad-account-for-staffhub-team-members-who-dont-have-one"></a>Vincular una cuenta de Azure AD a los miembros del equipo de StaffHub que no tengan una

Cada miembro del equipo de StaffHub debe estar vinculado a una cuenta de Azure Active Directory (Azure AD). Los usuarios de la organización no estarán vinculados a una cuenta de Azure AD si se aplica alguno de los escenarios siguientes:

- Un propietario de equipo agregó a un usuario que no tiene una cuenta de Azure AD.
- Un propietario del equipo ha invitado a un usuario a un equipo de StaffHub y ese usuario no aceptó la invitación.

Estos usuarios tienen cuentas inactivas y muestran un estado de usuario desconocido, invitado o InviteRejected. Puedes vincular una cuenta de Azure AD para estos usuarios.  A continuación, le mostramos cómo.

#### <a name="get-a-list-of-all-inactive-accounts-on-staffhub-teams"></a>Obtener una lista de todas las cuentas inactivas de los equipos de StaffHub

Ejecute la siguiente serie de comandos para obtener una lista de todas las cuentas inactivas de los equipos de StaffHub y exporte la lista a un archivo CSV. Cada comando debe ejecutarse por separado.

```PowerShell
$InvitedUsersObject = @()

$StaffHubTeams = Get-StaffHubTeamsForTenant

$StaffHubTeams[0] = $StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq 'StaffHub' }

foreach($team in $StaffHubTeams[0])
{ 
    Write-host $team.name
    $StaffHubUsers = Get-StaffHubMember -TeamId $team.Id | where {$_.State -eq "Invited"}
    foreach($StaffHubUser in $StaffHubUsers) {
        $InvitedUsersObject  += New-Object PsObject -Property @{
          "TeamID"="$($team.Id)"
          "TeamName"="$($team.name)"
          "MemberID"="$($StaffHubUser.Id)"
            }
    }
}

$InvitedUsersObject | SELECT * | export-csv InvitedUsers.csv -NoTypeInformation  
```

#### <a name="link-the-account"></a>Vincular la cuenta

Realice una de las siguientes acciones:

- Convertir y vincular la cuenta.

  Los propietarios y administradores del equipo de StaffHub pueden convertir una cuenta inactiva y vincularla a una cuenta de Azure AD de StaffHub cambiando la dirección de correo electrónico del usuario a un UPN válido en la página de configuración del equipo de StaffHub.

- Quite la cuenta desvinculada y, a continuación, vuelva a agregar la cuenta con el UPN.
    1. Ejecute el cmdlet [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubMember?view=staffhub-ps) para quitar la cuenta no aprovisionada del equipo de StaffHub.
    2. Ejecute el cmdlet [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) para volver a agregar la cuenta al equipo de StaffHub mediante el UPN.

- Quitar la cuenta inactiva. Use esta opción si la cuenta de usuario ya no es necesaria.

### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a>Asignar la Directiva de configuración de la aplicación de FirstlineWorker a los usuarios

Teams incluye una directiva de configuración de aplicaciones de FirstlineWorker integrada que puede usar para personalizar Teams y resaltar las aplicaciones más importantes para los trabajadores de los Firstline de su organización. Cuando asigne esta directiva a los usuarios, las aplicaciones de la Directiva se anclarán a la barra de la aplicación de Teams para acceder a ellas de forma rápida y fácil. Puede encontrar otras aplicaciones agregadas a teams en la barra de aplicaciones haciendo clic en **... Más aplicaciones** en el escritorio de Teams y en los clientes Web, y deshaciendo el dedo hacia arriba en el cliente móvil de Teams. De forma predeterminada, la Directiva de configuración de la aplicación FirstlineWorker incluye las aplicaciones actividad, turnos, chat y llamadas.

Para conocer los pasos sobre cómo asignar la Directiva de configuración de la aplicación FirstlineWorker a los usuarios, consulte [usar la Directiva de configuración de la aplicación FirstlineWorker para anclar turnos a teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams). Después de asignar una directiva, puede demorar unas pocas horas en surtir efecto.

Le recomendamos que complete este paso al menos una semana antes de mover los equipos y usuarios de StaffHub a teams. Cuando los usuarios estén en Teams, asegúrese de que pueden ver y acceder a la aplicación turnos.

También puede crear directivas de configuración de aplicaciones personalizadas y editar la configuración en la Directiva configuración global de la aplicación. Para obtener más información, consulte [Administrar directivas de configuración de aplicaciones en Teams](../../teams-app-setup-policies.md).

### <a name="onboard-users-to-teams"></a>Usuarios incorporados a teams

Como parte de la estrategia de incorporación, proporcione formación e instrucciones a los usuarios para que puedan familiarizarse con los equipos. Comparta los siguientes recursos con los usuarios para que sepan dónde obtener los clientes, la formación y el soporte técnico de Teams:

- [Cliente web de Teams](https://teams.microsoft.com)
- [Vínculos de descarga del cliente de escritorio y móvil](https://teams.microsoft.com/downloads)
- [Vídeos de aprendizaje de Teams](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [Documentación de Ayuda de Teams](https://support.office.com/teams)

Para obtener instrucciones sobre la implementación de equipos y sobre la adopción de equipos, consulte [cómo implementar Teams](../../How-to-roll-out-teams.md) y [adoptar equipos](../../adopt-microsoft-teams-landing-page.md).

## <a name="conduct-a-pilot"></a>Realizar una prueba piloto

Le recomendamos que empiece por mover dos o tres equipos de StaffHub para un grupo seleccionado de primeras personas. La ejecución de un proyecto piloto le ayuda a afinar el plan de transición y a asegurarse de que está listo para mover todos los equipos de StaffHub de su organización a teams. También identifica a los campeones que pueden ayudar a impulsar la adopción en toda la organización. Si es una pequeña empresa que no necesita un enfoque por fases, es posible que los pasos de esta sección sean todo lo que necesita para cambiar de StaffHub a teams.

### <a name="identify-pilot-teams"></a>Identificar equipos piloto

Póngase en contacto con usted para identificar dos o tres equipos piloto. Todos los miembros del equipo deben confirmar el uso de turnos en Teams para administrar su programación y comunicarse y colaborar entre sí.

### <a name="identify-team-champions"></a>Identificar a los expertos en el equipo

Identifique a los campeones a través de equipos piloto y inscribalos para ayudar a repartir turnos. Los campeones del equipo son apasionados de lo que hacen, compartiendo su propio aprendizaje para ofrecer asistencia y orientación a los miembros del equipo. Los expertos del equipo pueden ser administradores o propietarios del equipo.

Los expertos en equipo deben asegurarse de que los miembros del equipo se configuren dedicando tiempo para que todos puedan [obtener clientes](../../get-clients.md)de equipo, iniciar sesión en Teams y consultar sus programaciones en turnos y empezar a conversar entre sí. Los usuarios que ya estén familiarizados con StaffHub se activarán y se ejecutarán rápidamente en turnos. También puede hacer que [desplace la ayuda](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) para obtener ayuda adicional.

### <a name="move-a-staffhub-team"></a>Mover un equipo de StaffHub

Siga estos pasos para mover un equipo de StaffHub a la vez. Recomendamos este enfoque para los equipos de la prueba piloto. Más adelante, cuando esté listo para mover todos los equipos de StaffHub de su organización, vea [mover los equipos de staffhub](#move-your-staffhub-teams) para conocer los pasos para mover varios equipos a la vez.

Ejecute lo siguiente para mover un equipo de StaffHub.

```PowerShell
Move-StaffHubTeam -TeamId <String>
```
Ejemplo

```PowerShell
Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

Este es un ejemplo de la respuesta que obtiene al enviar una solicitud para mover un equipo de StaffHub a teams.

```console
 jobId                                      teamId                                      teamAlreadyInMicrosofteams  
---------------------------------------    ----------------------------------------    ---------------------------          
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

Para comprobar el estado de una solicitud de movimiento, ejecute lo siguiente.

```PowerShell
Get-TeamMigrationJobStatus <String>
```
Ejemplo

```PowerShell
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"
```

Este es un ejemplo de la respuesta que obtiene cuando hay un movimiento en curso.

```console
jobId                                     status       teamId                                     isO365GroupCreated  Error
----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

### <a name="move-files-from-a-staffhub-team-to-teams"></a>Mover archivos de un equipo de StaffHub a teams

Este paso solo se aplica si el equipo de StaffHub que movió a teams tiene archivos que también desea mover a teams. Puede mover archivos directamente en SharePoint Online o mediante PowerShell.

#### <a name="in-sharepoint-online"></a>En SharePoint Online

Vea [Cómo mover archivos en SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).

#### <a name="using-powershell"></a>Con PowerShell

Descargue e instale el [Shell de administración de SharePoint Online](https://www.microsoft.com/download/details.aspx?id=35588), si todavía no lo ha hecho. Contiene los cmdlets que necesita para mover los archivos.  

Use el cmdlet [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) para conectarse al sitio de grupo de SharePoint Online.

```PowerShell
Connect-PnPOnline -Url https://<sharepoint URL>/sites/<Group Name>  
```

Para cada archivo que desee mover de StaffHub a Teams, use el cmdlet [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) para mover el archivo.

```PowerShell
Move-PnPFile -ServerRelativeUrl "/sites/<Group Name>/Shared Documents/<File Name>" -TargetUrl "/sites/<Group Name>/Shared Documents/General/<File Name>" 
```

Para mover varios archivos, recorra los archivos y ejecute el segundo comando en el bucle. No es necesario que repitas el primer comando si la sesión sigue activa.

## <a name="go-beyond-your-pilot-and-move-all-staffhub-teams"></a>Vaya más allá de la prueba piloto y mueva todos los equipos de StaffHub

### <a name="raise-awareness"></a>Aumentar el conocimiento

Cuando esté listo para ir más allá de los equipos piloto y mover los equipos de StaffHub de su organización a Teams, es importante comunicar primero el cambio en toda la organización. Represente la palabra acerca de los turnos y la transición a Teams para aumentar la conciencia, generar entusiasmo y adopción de unidades.

### <a name="move-your-staffhub-teams"></a>Mover los equipos de StaffHub

Siga estos pasos para mover equipos de StaffHub de forma masiva. Puede elegir mover todos los equipos de StaffHub de su organización o mover determinados equipos de StaffHub. Si quiere mover los equipos de StaffHub de uno en uno, vea [mover un equipo de staffhub](#move-a-staffhub-team).

#### <a name="move-all-staffhub-teams"></a>Mover todos los equipos de StaffHub

Ejecute lo siguiente para obtener una lista de todos los equipos de StaffHub de su organización.

```PowerShell
$StaffHubTeams = Get-StaffHubTeamsForTenant

$StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq 'StaffHub' }
```

A continuación, ejecute lo siguiente para mover todos los equipos.

```PowerShell
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

Este es un ejemplo de la respuesta.

En el caso de cualquier equipo que ya se haya movido a teams o que ya exista en Teams, jobId tendrá el valor "null", ya que no es necesario enviar el trabajo para mover ese equipo.

```console
jobId                                      teamId                                      teamAlreadyInMicrosofteams  
----------------------------------------   -----------------------------------------   --------------------------         
null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams"></a>Mover equipos de StaffHub específicos

Ejecute el siguiente procedimiento para obtener una lista de todos los identificadores de equipo de StaffHub en su organización.

```PowerShell
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

En los resultados devueltos por el `Get-StaffHubteamsForTenant` cmdlet que ejecutó anteriormente, seleccione los identificadores de equipo que desea mover y agréguelos a un archivo de valores separados por comas (CSV).

Este es un ejemplo de cómo se debe dar formato al archivo CSV.

|Identificar  |
|---------|
|TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f<br>TEAM_81b1f191-3e19-45ce-AB32-3ef51f100000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000|

Después de crear el archivo CSV, ejecute lo siguiente para mover los equipos especificados en el archivo CSV.

```PowerShell
$StaffHubTeams = Import-Csv .\teams.csv

foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams"></a>Confirmar que los equipos de StaffHub se movieron a teams

Ejecute lo siguiente para obtener una lista de todos los equipos de los turnos de su organización. 

```PowerShell
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

### <a name="move-files-from-your-staffhub-teams-to-teams"></a>Mover archivos de los equipos de StaffHub a teams

Si los equipos de StaffHub que movió contiene archivos que también desea mover a Teams, vea [mover archivos de un equipo de staffhub a teams](#move-files-from-a-staffhub-team-to-teams).

## <a name="monitor-teams-usage"></a>Supervisar el uso de Teams

Los informes de uso pueden ayudarlo a comprender mejor los patrones de uso y le proporcionan información sobre cómo priorizar los esfuerzos de aprendizaje y comunicación en toda la organización. Puede ejecutar informes que muestran el uso general de los equipos, los tipos de actividades que los usuarios realizan en Teams, cómo se conectan los usuarios a teams y mucho más. Para obtener más información, vea informes [de equipos en el centro de administración de Microsoft Teams](../../teams-analytics-and-reports/teams-reporting-reference.md) y [informes de actividades de Teams en el centro de administración de Microsoft 365](../../teams-activity-reports.md).

## <a name="troubleshooting"></a>Solución de problemas

**Cómo obtener más información sobre errores**

Ejecute lo siguiente para obtener más información sobre los errores de "error" que se producen al intentar mover un equipo:

```PowerShell
Move-StaffHubTeam -TeamId <TeamId>

$res = Get-TeamMigrationJobStatus -JobId <JobId>

$res.Status
```

Verá uno de los siguientes Estados devuelto: Succeed, Failure, Ingress, queued.

Si se devuelve "Failure", ejecute lo siguiente para obtener más información sobre el error:

```PowerShell
$res.Result.Error.Innererror
```

**Al intentar mover un equipo de StaffHub, el estado se muestra como "error" y recibe un mensaje de error "no se pudo recuperar las categorías de SKU aplicables para el usuario"**

Esto puede ocurrir si uno o más miembros del equipo no tienen una licencia de Teams. Vaya a portal.office.com, busque el grupo y, a continuación, confirme que se asigna una licencia de Teams a los miembros del grupo.

**Al intentar mover un equipo de StaffHub, el estado se muestra como "error" y recibe el mensaje de error "no se encontró el propietario del equipo"**

Esto puede ocurrir si el grupo que está asociado al equipo de StaffHub no tiene un propietario del equipo. Vaya a portal.office.com, busque el grupo y, a continuación, agregue uno o más propietarios al grupo.

**Al intentar mover archivos de StaffHub a Teams, recibe el mensaje de error "Permiso denegado".**

Esto puede ocurrir si está intentando mover archivos en un grupo privado de Microsoft 365 del que no es miembro. Si este es el caso, use el cmdlet [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) para agregarse al equipo de StaffHub y, a continuación, mueva los archivos. Después de mover los archivos, use el cmdlet [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) para quitarse del equipo. 

**Al intentar mover archivos de StaffHub a Teams, recibe un error que indica que no existe la carpeta general.**

Ejecute el siguiente comando para agregar la carpeta general a SharePoint y, a continuación, vuelva a intentarlo:

  ```PowerShell
  Add-PnPFolder -Name General -Folder 'Shared Documents'
  ```  

## <a name="related-topics"></a>Temas relacionados
- [Cómo implementar Microsoft Teams](../../How-to-roll-out-teams.md)
- [Se retirará Microsoft StaffHub](microsoft-staffhub-to-be-retired.md)
- [Administrar la aplicación Turnos para su organización en Microsoft Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Referencia de PowerShell de StaffHub](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
