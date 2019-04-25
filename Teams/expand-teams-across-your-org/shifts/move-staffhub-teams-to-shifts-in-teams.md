---
title: Mover los equipos de StaffHub a Turnos en Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 3/29/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo mover los equipos de Microsoft StaffHub y programar datos a turnos en Microsoft Teams.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 14f94428ddeba7b5a648b4b8dbd7bd5ef8fae0e4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32246103"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a>Mover los equipos de Microsoft StaffHub a turnos en Microsoft Teams

> [!IMPORTANT]
> Eficaces se deben retirarse el 1 de octubre de 2019, Microsoft StaffHub. Capacidades de StaffHub que estamos creando en Microsoft Teams. En la actualidad, los equipos incluye la aplicación de turnos para la administración de programación y funciones adicionales se lleve a cabo a través del tiempo. StaffHub dejará de funcionar para todos los usuarios en el 1 de octubre de 2019. Cualquier persona que intenta abrir StaffHub se mostrará un mensaje que les dirige a descargar los equipos. Para obtener más información, vea [Microsoft StaffHub retirarse](microsoft-staffhub-to-be-retired.md).

> Aún no se ha emitido la funcionalidad descrita en este artículo. Se ha anunciado y estará disponible próximamente, hacia el final de abril de 2019. Si usted es un administrador, puede saber cuándo estará disponible en el centro de mensajes (en el [Centro de administración de Microsoft 365](https://portal.office.com/adminportal/home)).

La aplicación de turnos en los equipos proporciona un método sencillo para administración de programaciones y el flujo constante de MAYÚS permutaciones y cancelaciones que se producen en un diario. Los miembros del equipo pueden tener acceso a su programación y MAYÚS información directamente en la aplicación y a través de sus dispositivos para establecer sus preferencias, administrar sus programaciones y tiempo de la solicitud desactivado.

En este artículo le guiará a través del procedimiento para mover los equipos de su organización StaffHub y programar datos a turnos en los equipos. Independientemente de si una empresa pequeña con uno o dos equipos de StaffHub o una empresa grande con cientos de equipos StaffHub, aquí encontrará la orientación de administración que necesita para ayudar a hacer la transición a los equipos se realice correctamente.

Debe ser un administrador global para llevar a cabo los pasos de este artículo. Si aún no lo ha hecho, eche un vistazo a través de la [retirada de StaffHub preguntas más frecuentes](microsoft-staffhub-to-be-retired.md) para obtener respuestas a cualquier pregunta que tenga. 

## <a name="what-you-need-to-know-about-the-move-to-teams"></a>Lo que necesita saber sobre el movimiento para los equipos

### <a name="when-to-move-to-teams"></a>Cuándo se deben mover a los equipos

Eficaces se deben retirarse el 1 de octubre de 2019, StaffHub. Le animamos a empezar a usar los equipos de hoy en día y empezar a realizar la transición de los equipos y usuarios de StaffHub de su organización. Con la administración de programación que se va a la característica usan con más frecuencia en StaffHub, se recomienda que usar la aplicación de turnos en los equipos en el futuro.

### <a name="what-is-moved-to-teams"></a>¿Qué se mueve a los equipos

Detalles del usuario, la información de programación y datos de chat y de archivo son la transición a los equipos. Esto incluye los miembros del equipo, las programaciones de equipo y chats y los archivos de los últimos 90 días.

Cada equipo StaffHub necesita un grupo de 365 Office correspondiente. Si un equipo StaffHub no tiene un grupo de Office 365 asociados con ella, uno se crea automáticamente para que admitir la transición. Teniendo en cuenta la diferencia en el equipo y la asignación de nombres de grupo entre los equipos y StaffHub, es posible que vea un nombre de equipo diferente en los equipos.

Como hacer la transición de los equipos de StaffHub a los equipos, los usuarios ya no tendrán acceso a sus programaciones en StaffHub y se redirigen a turnos en los equipos. Se recomienda que comunicarse este cambio en toda la organización para minimizar las interrupciones y para animar a los usuarios a adoptar y explorar los equipos.

## <a name="prepare"></a>Preparar

Aquí es cómo prepararse para mover a los equipos.

### <a name="assign-teams-licenses"></a>Asignar licencias de Teams

Cada usuario debe tener una licencia de Microsoft 365 u Office 365 activada desde [un plan de elegible](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) y se debe asignar una licencia de los equipos. Asignación de una licencia de los equipos a los usuarios les proporciona acceso a los equipos.

Administrar las licencias de los equipos en el centro de administración de Microsoft 365. Para obtener más información, vea [administrar el acceso de usuarios a los equipos](../../user-access.md).

> [!NOTE]
> Si la organización usa Skype para la empresa y no está listo para mover todos los usuarios a los equipos, puede habilitar los equipos para su Firstline a los trabajadores que, a continuación, puede ejecutar los equipos junto con Skype para la empresa. En este modo de coexistencia, llamado *Islas*, cada aplicación cliente funciona como una solución independiente. Para obtener más información, vea [Descripción de los equipos y Skype para la interoperabilidad y coexistencia de negocio](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a>Aprovisionamiento de cuentas para los usuarios de StaffHub que no tienen una identidad en Azure AD

Cada administrador y miembro del equipo deben tener una identidad en Azure Active Directory (AD Azure). Si un usuario ya no tiene una identidad en Azure AD, aprovisionar una cuenta para ellos. Le mostramos cómo.

- Los administradores y propietarios de equipo StaffHub pueden convertir una cuenta ficticia o inactiva y vincularlo a una cuenta proporcionada en StaffHub cambiando la dirección de correo electrónico del usuario a un UPN válido en la página de configuración del equipo de StaffHub.

- Los administradores pueden ejecutar el [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) y cmdlets de [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) para quitar una cuenta que no sean aprovisionado de un equipo de StaffHub y agregue la cuenta de back-usando el UPN.

### <a name="install-the-staffhub-powershell-module"></a>Instalar el módulo de PowerShell de StaffHub

Si no lo ha hecho ya, [instale el módulo de StaffHub PowerShell](install-the-staffhub-powershell-module.md).

Cuando se mueve un equipo de StaffHub, la solicitud de movimiento comprueba los requisitos previos. Aquí es motivos de por qué puede producir un error de una solicitud de movimiento:

- El usuario ha iniciado sesión no es un administrador global
- Los equipos se deshabilita para todos los usuarios en el inquilino
- Creación de grupos de Office 365 está deshabilitada en el inquilino
- La teamId StaffHub no es válido o no tiene ningún miembro
- El equipo de StaffHub incluye a miembros que no están vinculados a una cuenta de Azure AD  

## <a name="run-a-pilot"></a>Ejecutar una prueba piloto

Se recomienda que inicie moviendo dos o tres equipos de StaffHub para un grupo seleccionado de los primeros usuarios. Ejecutar a una prueba piloto le ayuda a refinar el plan de transición y asegúrese de que está listo para mover los equipos de StaffHub de todos los de su organización a los equipos. Se identifican los Campeones que pueden ayudar a estimular la adopción en toda la organización. Si usted es una empresa pequeña que no necesita un enfoque por fases, los pasos descritos en esta sección pueden ser todo lo que necesita para realizar el cambio de StaffHub a los equipos.

### <a name="identify-pilot-teams"></a>Identificar los equipos pilotos

Llegar a identificar dos o tres equipos pilotos. Todos los miembros del equipo deben confirmar al uso de turnos en los equipos a administrar sus programaciones y comunicarse y colaborar con cada una de las demás.

### <a name="identify-team-champions"></a>Identificar a campeones de equipo

Identificar a campeones entre los equipos pilotos y dar de alta para ayudar a dé a conocer turnos. Campeones de equipo son entusiastas sobre lo que hacen, uso compartido de sus propios conocimientos para ofrecer soporte técnico y orientación a los miembros del equipo. Campeones de equipo pueden ser propietarios de equipo o los administradores.

Deben asegurarse de campeones de equipo los integrantes del grupo están configurar por dedique tiempo para todos los usuarios para [obtener a los clientes de los equipos](../../get-clients.md), inicie sesión en los equipos y desproteger sus programaciones por turnos e inicio charlar con cada una de las demás. Los usuarios que ya están familiarizados con StaffHub será y en funcionamiento rápidamente por turnos. También puede indicarles que [Ayudarán a turnos](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) para obtener más ayuda.

### <a name="move-a-staffhub-team-coming-soon"></a>Mover un equipo de StaffHub (próximamente)

Siga estos pasos para mover un equipo de StaffHub a la vez. Se recomienda este enfoque para los equipos de prueba piloto. Más adelante, cuando esté listo para mover los equipos de StaffHub de todos los de su organización, consulte [mover sus equipos StaffHub](#move-your-staffhub-teams-coming-soon) para obtener instrucciones acerca de cómo mover varios equipos a la vez.

Ejecute el siguiente procedimiento para mover un equipo StaffHub.

```
Move-StaffHubTeam -TeamId <String>

Sample:

Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

Este es un ejemplo de la respuesta que se obtiene al enviar una solicitud para mover un equipo de StaffHub a los equipos.

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

Para comprobar el estado de una solicitud de movimiento, ejecute lo siguiente.

```
Get-TeamMigrationJobStatus <String>

Sample:
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"

```

Este es un ejemplo de la respuesta que se obtiene cuando un movimiento está en curso.

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

## <a name="make-the-transition-from-staffhub-to-teams"></a>Realizar la transición desde StaffHub a los equipos

### <a name="raise-awareness"></a>Mejorar el conocimiento

Cuando esté listo para ir más allá de sus equipos pilotos y mover los equipos de su organización StaffHub a los equipos, es importante comunicarse en primer lugar el cambio a través de la organización. Propagar la palabra acerca de turnos y la transición a los equipos para mejorar el conocimiento, generar diversión y adopción de unidad.

### <a name="move-your-staffhub-teams-coming-soon"></a>Mover los equipos de StaffHub (próximamente)

Siga estos pasos para mover los equipos de StaffHub de forma masiva. Puede elegir mover los equipos de StaffHub de todos los de su organización o mover determinados equipos StaffHub. Si desea mover que los equipos StaffHub uno a la vez, consulte [mover un equipo StaffHub](#move-a-staffhub-team-coming-soon).

#### <a name="move-all-staffhub-teams-coming-soon"></a>Mover todos los equipos de StaffHub (próximamente)

Ejecute el siguiente procedimiento para obtener una lista de todos los equipos de StaffHub en su organización.

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

A continuación, ejecute el siguiente procedimiento para mover todos los equipos.

```
$StaffHubTeams | foreach {Move-StaffHubTeam -TeamId {$_.Id}}
```

Este es un ejemplo de la respuesta.

Para cualquier equipo que ya se ha movido a los equipos o ya existe en los equipos, jobId será "null" como un trabajo no es necesario que se debe enviar para mover ese equipo.

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams-coming-soon"></a>Mover determinados equipos StaffHub (próximamente)

Ejecute el siguiente procedimiento para obtener una lista de todos los StaffHub equipo identificadores en su organización.

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

En los resultados devueltos por la `Get-StaffHubteamsForTenant` cmdlet ejecutó anteriormente, seleccione los identificadores de equipo que desea mover y, a continuación, agregarlas a un archivo de valores separados por comas (CSV).

Este es un ejemplo de cómo se debe aplicar el formato de archivo CSV.

|Id.  |
|---------|
|TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f<br>TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000<br>TEAM_b42d0fa2 - 0fc 9-408b-85ff-c14a26700000<br>TEAM_b42d0fa2 - 0fc 9-408b-85ff-c14a26700000|

Después de crear el archivo CSV, ejecute el siguiente procedimiento para mover los equipos que especificó en el archivo CSV.

```
Import-Csv .\teams.txt | foreach {Move-StaffHubTeam -TeamdId {$_.Id}}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams-coming-soon"></a>Confirme que los equipos de StaffHub se han movido a los equipos (próximamente)

Ejecute el siguiente procedimiento para obtener una lista de todos los equipos de turnos en su organización. 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

## <a name="monitor-teams-usage"></a>Supervisar el uso de los equipos

Informes de uso le ayudarán a comprender los patrones de uso mejor y proporcionan una perspectiva sobre dónde asignar prioridades a los esfuerzos de aprendizaje y la comunicación en toda la organización. Dado que turnos es una aplicación en los equipos, puede ver el uso a través de informes de los equipos. Para obtener más información, vea [creación de informes de los equipos en el centro de administración de equipos de Microsoft](../../teams-analytics-and-reports/teams-reporting-reference.md) e [informes de actividad de los equipos en el centro de administración de Microsoft 365](../../teams-activity-reports.md).

## <a name="related-topics"></a>Temas relacionados
- [Se retirará Microsoft StaffHub](microsoft-staffhub-to-be-retired.md)
- [Administrar la aplicación Turnos para su organización en Microsoft Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Referencia de StaffHub PowerShell](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
