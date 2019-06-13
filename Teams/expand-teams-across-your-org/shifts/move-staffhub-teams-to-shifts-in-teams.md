---
title: Mover los equipos de StaffHub a Turnos en Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo programar datos y mover los equipos de Microsoft StaffHub a Turnos en Microsoft Teams.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e2e8b0ac4f1c4eb0cce2cae97481fc428f588ec5
ms.sourcegitcommit: 8f9bf1acdcdc2104fa8c343c030d64838e2c31eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2019
ms.locfileid: "34780812"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a>Mover los equipos de Microsoft StaffHub a Turnos en Microsoft Teams

> [!IMPORTANT]
> A partir del 1 de octubre de 2019, se retirará Microsoft StaffHub. Estamos creando las funciones de StaffHub en Microsoft Teams. En la actualidad, Teams incluye la aplicación Turnos para la administración de la programación y, a lo largo del tiempo, se implementarán funciones adicionales. StaffHub dejará de funcionar para todos los usuarios el 1 de octubre de 2019. A cualquier usuario que intente abrir StaffHub se mostrará un mensaje en el que se le indicará que descargue Teams. Para obtener más información, vea [Se retirará Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).

La aplicación Turnos de Teams ofrece un enfoque sencillo para administrar la programación y el flujo constante de las intercambios de turnos y de las cancelaciones que se producen diariamente. Los miembros del equipo pueden acceder a su programación, cambiar la información directamente en la aplicación y en todos sus dispositivos para establecer las preferencias, administrar la programación y solicitar tiempo libre.

En este artículo se mostrará cómo programar datos y mover los equipos de StaffHub de la organización a Turnos en Teams. Este tema abarca:

- [Todo lo que debe saber sobre el movimiento a Teams](#what-you-need-to-know-about-the-move-to-teams)
- [Preparación](#prepare)
- [Realizar una prueba piloto](#conduct-a-pilot) 
- [Ir más allá de la prueba piloto y mover todos los equipos de StaffHub](#go-beyond-your-pilot-and-move-all-staffhub-teams)
- [Supervisar el uso de Teams](#monitor-teams-usage)
- [Solución de problemas](#troubleshooting)

Tanto si una empresa pequeña con uno o dos equipos de StaffHub como si es una gran empresa con cientos de equipos de StaffHub, aquí encontrará las instrucciones para administradores que necesita para que la transición a Teams se realice correctamente.

Debe ser un administrador global para realizar los pasos de este artículo. Si aún no lo ha hecho, consulte las [Preguntas frecuentes sobre el retiro de StaffHub](microsoft-staffhub-to-be-retired.md) para obtener respuestas a las preguntas que pueda tener.

## <a name="what-you-need-to-know-about-the-move-to-teams"></a>Todo lo que debe saber sobre el movimiento a Teams

### <a name="when-to-move-to-teams"></a>Cuándo moverse a Teams

A partir del 1 de octubre de 2019, se retirará StaffHub. Le recomendamos que empiece a usar Teams hoy y que empiece a realizar la transición de los equipos y usuarios de la organización desde StaffHub. Como la administración de programación es la característica más usada de StaffHub, le recomendamos usar en el futuro la aplicación Turnos en Teams.

### <a name="what-is-moved-to-teams"></a>Qué se mueve a Teams

Los detalles de los usuarios, la información de programación, el chat y los datos de los archivos pasan a Teams. Esto incluye la subscripción de equipo, la programación de equipo, los chats y los archivos de los últimos 90 días.

Cada equipo de StaffHub necesita un correspondiente grupo de Office 365. Si un equipo de StaffHub no tiene un grupo de Office 365 asociado, se crea uno automáticamente para dar soporte a la transición. Debido a la diferencia de nombres de equipo y grupo entre Teams y StaffHub, es posible que vea un nombre de equipo distinto en Teams.

Al realizar la transición de los equipos de StaffHub a Teams, los usuarios ya no tienen acceso a su programación en StaffHub y serán dirigidos a Turnos en Teams. Le recomendamos que comunique este cambio en toda la organización para minimizar las interrupciones y animar a los usuarios a adoptar y explorar Teams. Si tiene Azure AD Premium, puede [ejecutar un informe](run-report-to-show-staffhub-usage.md) para obtener una lista de los usuarios de StaffHub de la organización que necesitan saber sobre este cambio.  

No hay ninguna opción de reversión después de mover un equipo de StaffHub a Teams.

### <a name="user-experience-when-you-move-a-team"></a>Experiencia del usuario al mover un equipo

Al cambiar el equipo de StaffHub a Turnos en Teams, el tiempo de inactividad de los usuarios es mínimo (menos de un segundo, si lo hay). Los usuarios pueden seguir usando StaffHub hasta que se complete el movimiento a Teams. Cuando haya finalizado el movimiento, los miembros del equipo verán un mensaje que les informa de que necesitan empezar a usar Teams en Teams para tener acceso a su programación de equipo. Este es un ejemplo del mensaje que los usuarios ven en StaffHub después de mover el equipo de StaffHub a Teams.

![Ejemplo del mensaje que verán los usuarios.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Ejemplo del mensaje que los usuarios ven en StaffHub después de mover el equipo de StaffHub a Teams")

## <a name="prepare"></a>Preparación

Aquí le mostramos cómo prepararse para el movimiento a Teams.

### <a name="check-that-prerequisites-are-met"></a>Comprobar que se cumplen los requisitos previos

Antes de mover un equipo de StaffHub a Teams, asegúrese de lo siguiente:

- El usuario que ha iniciado sesión es un administrador global.
- Teams está habilitado para todos los usuarios del espacio empresarial.
- La creación de Grupos de Office 365 está habilitada en el espacio empresarial.
- El teamId de StaffHub es válido.
- El equipo de StaffHub contiene miembros. 
- Todos los miembros del equipo de StaffHub se vinculan a una cuenta de Azure AD. 

Si no se cumplen estos requisitos previos, se producirá un error en la solicitud de movimiento. 

### <a name="assign-teams-licenses"></a>Asignar licencias de Teams

Cada usuario debe tener una licencia de Office 365 o Microsoft 365 de [un plan válido](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) y se le debe asignar una licencia de Teams. La asignación de una licencia de Teams a los usuarios les da acceso a Teams.

Puede administrar las licencias de Teams en el Centro de administración de Microsoft 365. Para obtener más información, vea [Administrar el acceso de los usuarios a Teams](../../user-access.md).

> [!NOTE]
> Si la organización usa Skype Empresarial y usted no está listo para mover todos los usuarios a Teams, puede habilitar Teams para los Firstline Workers que pueden ejecutarlo junto con Skype Empresarial. En este modo de coexistencia, llamado *Aplicaciones aisladas*, todas las aplicaciones de cliente funcionan como soluciones independientes. Para obtener más información, vea [Entender la coexistencia y la interoperabilidad de Skype Empresarial y Teams](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).

### <a name="install-the-staffhub-powershell-module"></a>Instalar el módulo de PowerShell de StaffHub

Si aún no lo ha hecho, [instale el módulo de PowerShell de StaffHub](install-the-staffhub-powershell-module.md). 

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a>Aprovisionar cuentas para los usuarios de StaffHub que no tienen una identidad en Azure AD

Todos los administradores y miembros del equipo deben tener una identidad en Azure Active Directory (Azure AD). Si un usuario aún no tiene una identidad en Azure AD, proporcióneles una cuenta. A continuación, le mostramos cómo. 

#### <a name="get-a-list-of-all-users-on-staffhub-teams-that-have-team-members-that-arent-provisioned-with-an-azure-ad-account"></a>Obtener una lista de todos los usuarios de los equipos de StaffHub que tienen miembros del equipo que no están aprovisionados con una cuenta de Azure AD

Ejecute lo siguiente:
```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
foreach($team in $StaffHubTeams[0]) {Get-StaffHubMember -TeamId $team.Id | where {$_.Email -eq $null -or $_.State -eq "Invited"}}
```

#### <a name="provision-the-account"></a>Aprovisionar la cuenta

Siga uno de estos pasos:

- Convierta y vincule la cuenta a una cuenta aprovisionada.

  Los propietarios y administradores del equipo de StaffHub pueden convertir una cuenta ficticia o inactiva y vincularla a una cuenta aprovisionada en StaffHub cambiando la dirección de correo electrónico del usuario a un UPN válido en la página de configuración del equipo de StaffHub.

- Quite la cuenta sin aprovisionar y, después, vuelva a agregar la cuenta con el UPN.
    1. Ejecute el cmdlet [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) para quitar la cuenta sin aprovisionar del equipo de StaffHub.
    2. Ejecute el cmdlet [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) para volver a agregar la cuenta al equipo de StaffHub con el UPN. 

### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a>Asignar la directiva de configuración de la aplicación FirstlineWorker a los usuarios

Teams incluye una directiva integrada de configuración de la aplicación de FirstlineWorker que puede usar para personalizar Teams y resaltar las aplicaciones que son más importantes para los Firstline Workers de la organización. Cuando asigna esta directiva a los usuarios, las aplicaciones de la directiva se anclan a la barra de la aplicación de Teams para acceder de forma rápida y fácil. Se pueden encontrar otras aplicaciones agregadas a Teams en la barra de la aplicación haciendo clic en **... Más aplicaciones** en los clientes para equipos de escritorio y web, y desplazando hacia arriba en la aplicación móvil de Teams. De forma predeterminada, la directiva de configuración de la aplicación FirstlineWorker incluye las aplicaciones Actividad, Turnos, Chat y Llamadas.

Para conocer los pasos para asignar la directiva de configuración de la aplicación FirstlineWorker a los usuarios, vea [Usar la directiva de configuración de la aplicación FirstlineWorker para anclar Turnos a Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams). Después de asignar una directiva, puede tardar hasta 24 horas en surtir efecto.

Le recomendamos que realice este paso por lo menos una semana antes de mover los equipos y usuarios de StaffHub a Teams. Cuando los usuarios se encuentren en Teams, compruebe que pueden ver y acceder a la aplicación Turnos.

También puede crear directivas de configuración de aplicaciones personalizadas y editar la configuración en la directiva de configuración global de la aplicación. Para obtener más información, consulte [Administrar directivas de configuración de aplicaciones en Teams](../../teams-app-setup-policies.md).

### <a name="onboard-users-to-teams"></a>Incorporar usuarios a Teams

Como parte de la estrategia de incorporación, proporcione formación e instrucciones para ayudar a los usuarios a familiarizarse con Teams. Comparta los siguientes recursos con los usuarios para que sepan dónde obtener clientes, formación y soporte técnico de Teams:

- [Cliente web de Teams](https://teams.microsoft.com)
- [Vínculos de descarga del cliente de escritorio y móvil](https://teams.microsoft.com/downloads)
- [Vídeos de aprendizaje de Teams](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [Documentación de Ayuda de Teams](https://support.office.com/teams)

Para obtener instrucciones sobre cómo implementar Teams y para impulsar su adopción, vea [Cómo implementar Teams](../../How-to-roll-out-teams.md) y [Adoptar Teams](../../adopt-microsoft-teams-landing-page.md).

## <a name="conduct-a-pilot"></a>Realizar una prueba piloto

Le recomendamos que comience moviendo dos o tres equipos de StaffHub para un grupo selecto de usuarios pioneros. La ejecución de una prueba piloto le ayuda a afinar su plan de transición y a asegurarse de que está preparado para mover todos los equipos de StaffHub de la organización a Teams. También identifica a los expertos que pueden ayudar a impulsar la adopción en toda la organización. Si es una empresa pequeña que no necesita un enfoque por fases, los pasos de esta sección pueden ser todo lo que necesita para realizar el cambio de StaffHub a Teams.

### <a name="identify-pilot-teams"></a>Identificar equipos piloto

Póngase en contacto para identificar dos o tres equipos piloto. Todos los miembros del equipo deben confirmar el uso de Turnos en Teams para administrar su programación, comunicarse y colaborar entre sí.

### <a name="identify-team-champions"></a>Identificar a los expertos del equipo

Identifique a los expertos en los equipos piloto e inscríbalos para que ayuden a dar información sobre Turnos.  Los expertos de equipo están muy apasionados por lo que hacen, compartiendo sus propios conocimientos para ofrecer soporte técnico e instrucciones a los miembros del equipo. Los expertos del equipo pueden ser propietarios o administradores del equipo.

Los expertos del equipo deben asegurarse de que los miembros del equipo están preparados, dedicando tiempo para todos para que puedan [obtener clientes de Teams](../../get-clients.md), iniciar sesión en Teams, consultar su programación en Turnos y empezar el chat entre sí. Los usuarios que ya conocen StaffHub se pondrán en marcha rápidamente en Turnos. También puede aconsejarles [Ayuda de Turnos](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) para obtener ayuda adicional.

### <a name="move-a-staffhub-team"></a>Mover un equipo de StaffHub

Siga estos pasos para mover un equipo de StaffHub a la vez. Se recomienda este enfoque para los equipos piloto. Más adelante, cuando esté listo para mover todos los equipos de StaffHub de la organización, vea [Mover los equipos de StaffHub](#move-your-staffhub-teams) para conocer los pasos para mover varios equipos a la vez.

Ejecute lo siguiente para mover un equipo de StaffHub:

```
Move-StaffHubTeam -TeamId <String>
```
Ejemplo:

```
Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

Este es un ejemplo de la respuesta que obtiene al enviar una solicitud para mover un equipo de StaffHub a Teams.

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

Para comprobar el estado de una solicitud de movimiento, ejecute lo siguiente:

```
Get-TeamMigrationJobStatus <String>
```
Ejemplo:

```
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"
```

Este es un ejemplo de la respuesta que obtiene cuando un movimiento está en curso.

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

### <a name="move-files-from-a-staffhub-team-to-teams"></a>Mover archivos de un equipo de StaffHub a Teams

Este paso solo se aplica si el equipo de StaffHub que ha movido a Teams tiene archivos que también quiere mover a Teams. Puede mover archivos directamente en SharePoint Online o con PowerShell. 

#### <a name="in-sharepoint-online"></a>En SharePoint Online

Vea [Cómo mover archivos en SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).

#### <a name="using-powershell"></a>Con PowerShell

Descargue e instale el [Shell de SharePoint Online Management](https://www.microsoft.com/download/details.aspx?id=35588), si aún no lo ha hecho.  Este contiene los cmdlets que necesita para mover los archivos.  

Use el cmdlet [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) para conectarse al sitio de grupo de SharePoint Online.

```
Connect-PnPOnline -Url https://<sharepoint URL>/sites/<Group Name>  
```

Para cada archivo que quiera mover de StaffHub a Teams, use el cmdlet [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) para mover el archivo.

```
Move-PnPFile -ServerRelativeUrl "/sites/<Group Name>/Shared Documents/<File Name>" -TargetUrl "/sites/<Group Name>/Shared Documents/General/<File Name>" 
```

Para mover varios archivos, ejecute un bucle en los archivos y ejecute el segundo comando del bucle. No es necesario repetir el primer comando si la sesión permanece activa.

## <a name="go-beyond-your-pilot-and-move-all-staffhub-teams"></a>Ir más allá de la prueba piloto y mover todos los equipos de StaffHub 

### <a name="raise-awareness"></a>Crear conciencia 

Cuando esté listo para ir más allá de los equipos piloto y mover los equipos de StaffHub de la organización a Teams, es importante que primero comunique el cambio a toda la organización. Informa a los usuarios sobre Turnos y la transición a Teams para crear conciencia, generar entusiasmo e impulsar la adopción.

### <a name="move-your-staffhub-teams"></a>Mover los equipos de StaffHub

Siga estos pasos para mover los equipos de StaffHub de forma masiva. Puede elegir mover todos los equipos de StaffHub de la organización o mover equipos de StaffHub específicos. Si quiere mover los equipos de StaffHub uno a la vez, vea [Mover un equipo de StaffHub](#move-a-staffhub-team).

#### <a name="move-all-staffhub-teams"></a>Mover todos los equipos de StaffHub

Ejecute lo siguiente para obtener una lista de todos los equipos de StaffHub dentro de la organización.

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

Después, ejecute lo siguiente para mover todos los equipos.

```
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

Este es un ejemplo de la respuesta:

Para cualquier equipo que ya se haya movido a Teams o que ya exista en Teams, jobId tendrá el valor "null", ya que no es necesario enviar un trabajo para mover ese equipo.

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams"></a>Mover equipos de StaffHub específicos

Ejecute lo siguiente para obtener una lista de todos los Id. de equipo de StaffHub de la organización.

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

En los resultados devueltos por el cmdlet `Get-StaffHubteamsForTenant` anteriormente ejecutado, seleccione los id. de los equipos que quiera mover y, después, agréguelos a un archivo de valores separados por comas (CSV).

Aquí tiene un ejemplo de cómo se debe dar formato al archivo CSV.

|Id  |
|---------|
|TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f<br>TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000|

Después de crear el archivo CSV, ejecute lo siguiente para mover los equipos especificados en el archivo CSV.

```
$StaffHubTeams = Import-Csv .\teams.csv
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams"></a>Confirmar que los equipos de StaffHub se movieron a Teams

Ejecute lo siguiente para obtener una lista de todos los equipos de Turnos de la organización. 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

### <a name="move-files-from-your-staffhub-teams-to-teams"></a>Mover archivos de los equipos de StaffHub a Teams

Si los equipos de StaffHub que movió contienen archivos que también quiere mover a Teams, vea [Mover archivos de un equipo de StaffHub a Teams.](#move-files-from-a-staffhub-team-to-teams)

## <a name="monitor-teams-usage"></a>Supervisar el uso de Teams

Los informes de uso pueden ayudarle a comprender mejor los patrones de uso y obtener información sobre cómo priorizar los esfuerzos de aprendizaje y comunicación en la organización. Como Turnos es una aplicación de Teams, puede ver el uso a través de informes de Teams. Para obtener más información, vea [Informes de Teams en el Centro de administración de Microsoft Teams](../../teams-analytics-and-reports/teams-reporting-reference.md) e [Informes de actividad de Teams en el Centro de administración de Microsoft 365](../../teams-activity-reports.md).

## <a name="troubleshooting"></a>Solución de problemas 

**Cuando intenta mover archivos de StaffHub a Teams, recibe el mensaje de error "Permiso denegado".**

Esto puede ocurrir si está intentando mover archivos a un grupo privado de Office 365 del que no es miembro. Si ocurre esto, use el cmdlet [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) para agregarse al equipo de StaffHub y, después, mueva los archivos. Después de mover los archivos, use el [cmdlet Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) para quitarse del equipo. 

**Cuando intenta mover archivos de StaffHub a Teams, obtiene un error que indica que la carpeta general no existe.**

Ejecute el comando siguiente para agregar la carpeta general a SharePoint y, después, vuelva a intentarlo:

  ```
  Add-PnPFolder -Name General -Folder 'Shared Documents'
  ```  

## <a name="related-topics"></a>Temas relacionados
- [Cómo implementar Microsoft Teams](../../How-to-roll-out-teams.md)
- [Se retirará Microsoft StaffHub](microsoft-staffhub-to-be-retired.md)
- [Administrar la aplicación Turnos para su organización en Microsoft Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Referencia de PowerShell de StaffHub](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
