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
description: Obtenga información sobre cómo mover los equipos de Microsoft StaffHub y programar datos para desplazarse por Microsoft Teams.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: b6354c2edd4d8504aeb2c84715b982f6bf793d33
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548297"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a>Mover los equipos de Microsoft StaffHub a turnos en Microsoft Teams

> [!IMPORTANT]
> A partir del 1 de octubre de 2019, Microsoft StaffHub se retirará. Estamos construyendo las capacidades de StaffHub en Microsoft Teams. En la actualidad, Teams incluye la aplicación de turnos para la administración de la programación, y las funciones adicionales se aplicarán a lo largo del tiempo. StaffHub dejará de funcionar para todos los usuarios el 1 de octubre de 2019. Cualquier persona que intente abrir StaffHub recibirá un mensaje para que pueda descargar Teams. Para obtener más información, consulte [Microsoft StaffHub para que se](microsoft-staffhub-to-be-retired.md)retirará.

> La funcionalidad tratada en este artículo todavía no se ha publicado. Se ha anunciado y pronto estará disponible a principios del 2019 de junio. Si es un administrador, puede averiguar cuándo estará disponible en el centro de mensajes (en el centro de administración de [Microsoft 365](https://portal.office.com/adminportal/home)).

La aplicación de turnos de Teams ofrece un enfoque simple para administrar las programaciones y el flujo constante de swaps y cancelaciones de turnos que se producen diariamente. Los miembros del equipo pueden acceder a su programación y desplazar la información directamente en la aplicación y en todos sus dispositivos para establecer sus preferencias, administrar sus programaciones y solicitar tiempo.

Este artículo le muestra cómo mover los equipos de StaffHub y programar datos para desplazarse por los equipos. Tanto si es una pequeña empresa con uno o dos equipos de StaffHub como si es una empresa grande con cientos de equipos de StaffHub, aquí encontrará las instrucciones para administradores que necesita para que la transición a teams se realice correctamente.

Debe ser administrador global para poder realizar los pasos de este artículo. Si todavía no lo ha hecho, consulte las [preguntas más frecuentes sobre la jubilación de StaffHub](microsoft-staffhub-to-be-retired.md) para obtener respuestas a las preguntas que pueda tener. 

## <a name="what-you-need-to-know-about-the-move-to-teams"></a>Lo que debe saber sobre el desplazamiento a teams

### <a name="when-to-move-to-teams"></a>Cuándo mover a teams

A partir del 1 de octubre de 2019, se retirará StaffHub. Le recomendamos que comience a usar Teams hoy y empiece a cambiar la transición de los equipos y usuarios de su organización de StaffHub. Con la administración de programación como la característica que se usa con más frecuencia en StaffHub, le recomendamos que use la aplicación turnos en Teams en el futuro.

### <a name="what-is-moved-to-teams"></a>Qué se mueve a teams

Los detalles del usuario, la información de programación y los datos de chat y de archivos están migrados a teams. Esto incluye la pertenencia a grupos, las programaciones de equipo y los chats y archivos de los últimos 90 días.

Cada equipo de StaffHub necesita un grupo de Office 365 correspondiente. Si un equipo de StaffHub no tiene asociado un grupo de Office 365, se crea uno automáticamente para que admita la transición. Dada la diferencia de nomenclatura de equipo y grupo entre Teams y StaffHub, es posible que vea un nombre de equipo diferente en Teams.

A medida que vaya migrando equipos de StaffHub a Teams, los usuarios ya no tendrán acceso a sus programaciones en StaffHub y se redirigirán a los equipos. Le recomendamos que comunique este cambio en toda la organización para minimizar las interrupciones y para animar a los usuarios a adoptar y explorar equipos. Si tiene Azure AD Premium, puede [ejecutar un informe](run-report-to-show-staffhub-usage.md) para obtener una lista de los usuarios de StaffHub de su organización que necesitan saber sobre este cambio.  

No hay ninguna opción de deshacer después de mover un equipo de StaffHub a teams.

### <a name="user-experience-when-you-move-a-team"></a>Experiencia de usuario al mover un equipo

El tiempo de inactividad es mínimo (menos de un segundo, si lo hay) para los usuarios cuando su equipo cambia de StaffHub a turnos en Teams. Los usuarios pueden seguir usando StaffHub hasta que se complete el cambio a teams. Cuando se haya completado el movimiento, los miembros del equipo verán un mensaje para informarles de que necesitan comenzar a usar turnos en Teams para acceder a su programación de equipo. Este es un ejemplo del mensaje que los usuarios ven después de que el equipo de StaffHub se mueva a teams.

![Ejemplo del mensaje que los usuarios ven.] (../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Ejemplo del mensaje que los usuarios ven en StaffHub después de mover el equipo de staffhub a teams")

## <a name="prepare"></a>Preparar

Aquí le mostramos cómo prepararse para desplazarse a teams.

### <a name="assign-teams-licenses"></a>Asignar licencias de Teams

Cada usuario debe tener una licencia activa de Microsoft 365 o de Office 365 de [un plan apto](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) y debe tener asignada una licencia de Teams. Asignar una licencia de Teams a los usuarios les da acceso a teams.

Administra las licencias de Teams en el centro de administración de Microsoft 365. Para obtener más información, vea [administrar el acceso de los usuarios a teams](../../user-access.md).

> [!NOTE]
> Si su organización usa Skype empresarial y no está listo para mover a todos los usuarios a Teams, puede habilitar a Teams para sus trabajadores de los Firstline, que luego pueden ejecutar equipos junto con Skype empresarial. En este modo de coexistencia, llamadas *islas*, cada aplicación cliente funciona como una solución independiente. Para obtener más información, consulte [comprender Teams y la interoperabilidad y coexistencia de Skype empresarial](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a>Aprovisionar cuentas para los usuarios de StaffHub que no tienen una identidad en Azure AD

Cada administrador y cada miembro del equipo debe tener una identidad en Azure Active Directory (Azure AD). Si un usuario aún no tiene una identidad en Azure AD, aprovisione una cuenta. Le mostramos cómo.

- Los propietarios y administradores del equipo de StaffHub pueden convertir una cuenta ficticia o inactiva y vincularla a una cuenta aprovisionada de StaffHub cambiando la dirección de correo electrónico del usuario a un UPN válido en la página de configuración del equipo de StaffHub.

- Los administradores pueden ejecutar los cmdlets [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) y [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) para quitar una cuenta no aprovisionada de un equipo de StaffHub y agregarla de nuevo con el UPN.

### <a name="install-the-staffhub-powershell-module"></a>Instalar el módulo de PowerShell de StaffHub

Si todavía no lo ha hecho, [Instale el módulo de PowerShell de StaffHub](install-the-staffhub-powershell-module.md).

Al mover un equipo de StaffHub, la solicitud de movimiento comprueba los requisitos previos. Estas son las razones por las que se puede producir un error en una solicitud de movimiento:

- El usuario que ha iniciado sesión no es un administrador global
- Teams está deshabilitado para todos los usuarios del espacio empresarial
- La creación de grupos de Office 365 está deshabilitada en el inquilino
- El teamId de StaffHub no es válido o no tiene miembros
- El equipo de StaffHub incluye miembros que no están vinculados a una cuenta de Azure AD  

## <a name="run-a-pilot"></a>Ejecutar una prueba piloto

Le recomendamos que empiece por mover dos o tres equipos de StaffHub para un grupo seleccionado de primeras personas. La ejecución de un proyecto piloto le ayuda a afinar el plan de transición y a asegurarse de que está listo para mover todos los equipos de StaffHub de su organización a teams. También identifica a los campeones que pueden ayudar a impulsar la adopción en toda la organización. Si es una pequeña empresa que no necesita un enfoque por fases, es posible que los pasos de esta sección sean todo lo que necesita para cambiar de StaffHub a teams.

### <a name="identify-pilot-teams"></a>Identificar equipos piloto

Póngase en contacto con usted para identificar dos o tres equipos piloto. Todos los miembros del equipo deben confirmar el uso de turnos en Teams para administrar su programación y comunicarse y colaborar entre sí.

### <a name="identify-team-champions"></a>Identificar a los expertos en el equipo

Identifique a los campeones a través de equipos piloto y inscribalos para ayudar a repartir turnos. Los campeones del equipo son apasionados de lo que hacen, compartiendo su propio aprendizaje para ofrecer asistencia y orientación a los miembros del equipo. Los expertos del equipo pueden ser administradores o propietarios del equipo.

Los expertos en equipo deben asegurarse de que los miembros del equipo se configuren dedicando tiempo para que todos puedan [obtener clientes](../../get-clients.md)de equipo, iniciar sesión en Teams y consultar sus programaciones en turnos y empezar a conversar entre sí. Los usuarios que ya estén familiarizados con StaffHub se activarán y se ejecutarán rápidamente en turnos. También puede hacer que desplace la [ayuda](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) para obtener ayuda adicional.

### <a name="move-a-staffhub-team-coming-soon"></a>Mover un equipo de StaffHub (próximamente)

Siga estos pasos para mover un equipo de StaffHub a la vez. Recomendamos este enfoque para los equipos de la prueba piloto. Más adelante, cuando esté listo para mover todos los equipos de StaffHub de su organización, vea [mover los equipos de staffhub](#move-your-staffhub-teams-coming-soon) para conocer los pasos para mover varios equipos a la vez.

Ejecute lo siguiente para mover un equipo de StaffHub.

```
Move-StaffHubTeam -TeamId <String>

Sample:

Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

Este es un ejemplo de la respuesta que obtiene al enviar una solicitud para mover un equipo de StaffHub a teams.

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

Este es un ejemplo de la respuesta que obtiene cuando hay un movimiento en curso.

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

## <a name="make-the-transition-from-staffhub-to-teams"></a>Realizar la transición de StaffHub a teams

### <a name="raise-awareness"></a>Aumentar el conocimiento

Cuando esté listo para ir más allá de los equipos piloto y mover los equipos de StaffHub de su organización a Teams, es importante comunicar primero el cambio en toda la organización. Represente la palabra acerca de los turnos y la transición a Teams para aumentar la conciencia, generar entusiasmo y adopción de unidades.

### <a name="move-your-staffhub-teams-coming-soon"></a>Mover los equipos de StaffHub (próximamente)

Siga estos pasos para mover equipos de StaffHub de forma masiva. Puede elegir mover todos los equipos de StaffHub de su organización o mover determinados equipos de StaffHub. Si quiere mover los equipos de StaffHub de uno en uno, vea [mover un equipo de staffhub](#move-a-staffhub-team-coming-soon).

#### <a name="move-all-staffhub-teams-coming-soon"></a>Mover todos los equipos de StaffHub (próximamente)

Ejecute lo siguiente para obtener una lista de todos los equipos de StaffHub de su organización.

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

A continuación, ejecute lo siguiente para mover todos los equipos.

```
$StaffHubTeams | foreach {Move-StaffHubTeam -TeamId {$_.Id}}
```

Este es un ejemplo de la respuesta.

En el caso de cualquier equipo que ya se haya movido a teams o que ya exista en Teams, jobId tendrá el valor "null", ya que no es necesario enviar el trabajo para mover ese equipo.

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams-coming-soon"></a>Mover equipos de StaffHub específicos (próximamente)

Ejecute el siguiente procedimiento para obtener una lista de todos los identificadores de equipo de StaffHub en su organización.

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

En los resultados devueltos `Get-StaffHubteamsForTenant` por el cmdlet que ejecutó anteriormente, seleccione los identificadores de equipo que desea mover y agréguelos a un archivo de valores separados por comas (CSV).

Este es un ejemplo de cómo se debe dar formato al archivo CSV.

|Identificar  |
|---------|
|TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f<br>TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000|

Después de crear el archivo CSV, ejecute lo siguiente para mover los equipos especificados en el archivo CSV.

```
Import-Csv .\teams.txt | foreach {Move-StaffHubTeam -TeamdId {$_.Id}}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams-coming-soon"></a>Confirmar que los equipos de StaffHub se han movido a Teams (próximamente)

Ejecute lo siguiente para obtener una lista de todos los equipos de los turnos de su organización. 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

## <a name="monitor-teams-usage"></a>Supervisar el uso de Teams

Los informes de uso pueden ayudarlo a comprender mejor los patrones de uso y le proporcionan información sobre cómo priorizar los esfuerzos de aprendizaje y comunicación en toda la organización. Como ShiftS es una aplicación en Teams, puede ver el uso mediante informes de Teams. Para obtener más información, vea informes [de equipos en el centro de administración de Microsoft Teams](../../teams-analytics-and-reports/teams-reporting-reference.md) y [informes de actividades de Teams en el centro de administración de Microsoft 365](../../teams-activity-reports.md).

## <a name="related-topics"></a>Temas relacionados
- [Se retirará Microsoft StaffHub](microsoft-staffhub-to-be-retired.md)
- [Administrar la aplicación Turnos para su organización en Microsoft Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Referencia de PowerShell de StaffHub](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
