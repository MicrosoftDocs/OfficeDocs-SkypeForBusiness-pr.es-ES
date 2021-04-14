---
title: Azure Sentinel y Microsoft Teams
author: MicrosoftHeidi
ms.author: tracyp
manager: dansimp
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Asesoría y aprendizaje de seguridad para administradores de IT acerca del uso de Sentinel para supervisar y buscar las amenazas que puedan surgir en Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: c3b2c37f7f3731b34abb5337bf954250e0c3564d
ms.sourcegitcommit: 046b020cee8af00a1d0e5f5866f847d42e8ad9a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51712772"
---
# <a name="azure-sentinel-and-microsoft-teams"></a>Azure Sentinel y Microsoft Teams

> [!IMPORTANT]
> Azure Sentinel ahora tiene un conector integrado. Para obtener más información, consulte [Conectar los registros de Office 365 a Azure Sentinel](/azure/sentinel/connect-office-365). Esta es la ruta recomendada para recopilar estos registros y sustituye los métodos de recopilación que se describen a continuación.

Teams desempeña un papel fundamental en la comunicación y en el uso compartido de datos en la nube de Microsoft 365. Dado que Teams toca tantas tecnologías en la nube, puede beneficiarse de análisis humanos y automatizados. Esto se aplica tanto a la *búsqueda en registros* como a la *supervisión de reuniones en tiempo real*. Estas soluciones las proporcionan los administradores de Azure Sentinel.

> [!NOTE]
> ¿Necesita un actualizador de Azure Sentinel? [Este artículo](/azure/sentinel/overview) es la solución..

## <a name="sentinel-and-microsoft-teams-activity-logs"></a>Registros de actividad de Sentinel y Microsoft Teams

El presente artículo se centra en la recopilación de los registros de actividad de los equipos en Azure Sentinel.

Sentinel permite a los administradores realizar la gestión de la seguridad en un solo lugar. Esto incluye administrar:

- Dispositivos de terceros
- Protección contra amenazas de Microsoft
- Cargas de trabajo de Microsoft 365

Los libros de trabajo y runbooks de Sentinel pueden hacer que la supervisión de la seguridad sea *sistemática*. Un buen primer paso en este proceso es recopilar los registros necesarios para el análisis.

> [!NOTE]
> Puede aparecer más de una suscripción a Microsoft 365 en la misma instancia de Azure Sentinel. Esto permite la supervisión [en tiempo real](/azure/sentinel/livestream) y la búsqueda de amenazas en los archivos de registro históricos. Los administradores podrán realizar búsquedas mediante [consultas entre recursos](/azure/azure-monitor/log-query/cross-workspace-query), es decir, dentro de un solo grupo de recursos, entre grupos de recursos o en otra suscripción.  

## <a name="step-1-collect-teams-logs-enable-audit-logs-in-microsoft-365"></a>Paso 1: Recopilar registros de Microsoft Teams: Habilitar registros de auditoría en Microsoft 365

Dado que Teams registra la actividad a través de Microsoft 365, los registros de auditoría no se recopilan de forma predeterminada. Active esta característica con [estos pasos](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off). Los datos de Microsoft Teams se recopilan en la auditoría de Microsoft 365, en *Audit.General*.

## <a name="step-2-connect-office-365-logs-to-azure-sentinel"></a>Paso 2: Conectar los registros de Office 365 a Azure Sentinel

Azure Sentinel proporciona un conector integrado para los registros de Office 365, que le permite incorporar datos de Teams en Azure Sentinel junto con otros datos de Office 365.
 
En Azure Sentinel, habilite el conector de datos de Office 365. Para más información, consulte la [documentación de Azure Sentinel](/azure/sentinel/connect-office-365).

## <a name="helpful-hunting-kql-queries"></a>Consultas útiles de búsqueda de KQL

Use estas consultas para familiarizarse con el entorno de equipos y datos de su equipo. El conocer cómo debe verse y comportarse el entorno es un excelente primer paso para reconocer una actividad sospechosa. Desde allí, puede llegar a la búsqueda de amenazas.

### <a name="federated-external-users-query"></a>Consulta de usuarios externos federados

Obtenga una lista de los sitios de Teams que tienen usuarios externos federados. Estos usuarios tienen un sufijo de UPN y/o nombre de dominio que no pertenece a su organización.

En esta consulta de ejemplo, la organización es propietaria de contoso.com.

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where parse_json(Members)[0].Role == 3
| project TeamName, Operation, UserId, Members
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
```

> [!TIP]
> Para más información sobre los tipos de acceso de invitado y externo en Teams, consulte [Comunicarse con usuarios de otras organizaciones](communicate-with-users-from-other-organizations.md) o la sección [Tipos de participante](teams-security-guide.md#participant-types) en la Guía de seguridad de Teams.

### <a name="who-recently-joined--whose-role-changed"></a>Quién se unió recientemente o cambió su rol

Consulte a un usuario específico para comprobar si se han agregado a un canal de Teams en los últimos siete días, o en una semana:

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members has "<DisplayName>" or Members has "<UserPrincipalName>"
| project TeamName, Operation, UserId, Members
```

Consulte si el rol de un usuario cambió para un equipo en los últimos siete días:

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| project TeamName, Operation, UserId, Members
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
| where Role == '1'
``` 

### <a name="external-users-from-unknown-or-new-organizations"></a>Usuarios externos de organizaciones desconocidas o nuevas

En Teams, puede agregar usuarios externos a su entorno o canales. Las organizaciones suelen tener un número limitado de asociaciones clave y agregar usuarios de entre estos asociados. Esta KQL se ocupa de los usuarios externos añadidos a los equipos que provienen de organizaciones que no han sido vistas o añadidas anteriormente.

Para más información, vea la consulta en el [centro de git de la comunidad de Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/ExternalUserFromNewOrgAddedToTeams.yaml).

### <a name="external-users-who-were-added-and-then-removed"></a>Usuarios externos que se añadieron y que luego fueron eliminados 

Los atacantes con algún nivel de acceso existente pueden agregar una nueva cuenta externa a los Teams para tener acceso a los datos y exfiltrarlos. También pueden quitar rápidamente a ese usuario para ocultar que ha realizado el acceso. Esta búsqueda busca cuentas externas que se agregan a Teams y se quitan rápidamente para ayudar a identificar comportamientos sospechosos.

Para más información, vea la consulta en el [centro de git de la comunidad de Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Detections/OfficeActivity/ExternalUserAddedRemovedInTeams.yaml).

### <a name="new-bot-or-application-added"></a>Se agregó un nuevo bot o aplicación

Microsoft Teams puede incluir aplicaciones o bots en un equipo para ampliar el conjunto de características (incluidas aplicaciones personalizadas y bots). En algunos casos, se puede usar una aplicación o bot para *la persistencia* en Teams sin necesidad de una cuenta de usuario y se puede obtener acceso a archivos y otros datos. Esta consulta busca aplicaciones o bots que son nuevos para Teams. 

Para más información, vea la consulta en el [centro de git de la comunidad de Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/NewBotAddedToTeams.yaml).

### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a>Cuentas de usuario que son propietarios de un gran número de equipos  

Los atacantes que buscan elevar sus privilegios pueden asignarse a sí mismos privilegios de propietario de un gran número de equipos diversos. *Normalmente*, los usuarios crean y poseen algunos equipos sobre temas específicos. Esta consulta de KQL busca comportamientos sospechosos.

Para más información, vea la consulta en el [centro de git de la comunidad de Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultiTeamOwner.yaml).

### <a name="many-team-deletions-by-a-single-user"></a>Muchas eliminaciones de equipo de un único usuario

Los atacantes pueden causar interrupciones y perjudicar proyectos y datos eliminando varios equipos. Dado que los equipos suelen ser eliminados por propietarios individuales, la eliminación centralizada de muchos equipos puede ser una señal de problemas. Esta KQL busca usuarios únicos que eliminan varios equipos.

Para más información, vea la consulta en el [centro de git de la comunidad de Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultipleTeamsDeletes.yaml).

### <a name="expanding-your-threat-hunting-opportunities"></a>Ampliar las oportunidades de búsqueda de amenazas

La combinación de consultas de recursos como Azure Active Directory (Azure AD) u otras cargas de trabajo de Office 365 puede usarse con consultas de Teams. Por ejemplo, combine la detección de patrones sospechosos en SigninLogs de Azure AD y use ese resultado mientras busca propietarios del equipo.

```Kusto
let timeRange = 1d;
let lookBack = 7d;
let threshold_Failed = 5;
let threshold_FailedwithSingleIP = 20;
let threshold_IPAddressCount = 2;
let isGUID = "[0-9a-z]{8}-[0-9a-z]{4}-[0-9a-z]{4}-[0-9a-z]{4}-[0-9a-z]{12}";
let azPortalSignins = SigninLogs
| where TimeGenerated >= ago(timeRange)
// Azure Portal only and exclude non-failure Result Types
| where AppDisplayName has "Azure Portal" and ResultType !in ("0", "50125", "50140")
// Tagging identities not resolved to friendly names
| extend Unresolved = iff(Identity matches regex isGUID, true, false);
// Lookup up resolved identities from last 7 days
let identityLookup = SigninLogs
| where TimeGenerated >= ago(lookBack)
| where not(Identity matches regex isGUID)
| summarize by UserId, lu_UserDisplayName = UserDisplayName, lu_UserPrincipalName = UserPrincipalName;
// Join resolved names to unresolved list from portal signins
let unresolvedNames = azPortalSignins | where Unresolved == true | join kind= inner (
   identityLookup ) on UserId
| extend UserDisplayName = lu_UserDisplayName, UserPrincipalName = lu_UserPrincipalName
| project-away lu_UserDisplayName, lu_UserPrincipalName;
// Join Signins that had resolved names with list of unresolved that now have a resolved name
let u_azPortalSignins = azPortalSignins | where Unresolved == false | union unresolvedNames;
let failed_signins = (u_azPortalSignins
| extend Status = strcat(ResultType, ": ", ResultDescription), OS = tostring(DeviceDetail.operatingSystem), Browser = tostring(DeviceDetail.browser)
| extend FullLocation = strcat(Location,'|', LocationDetails.state, '|', LocationDetails.city)
| summarize TimeGenerated = makelist(TimeGenerated), Status = makelist(Status), IPAddresses = makelist(IPAddress), IPAddressCount = dcount(IPAddress), FailedLogonCount = count()
by UserPrincipalName, UserId, UserDisplayName, AppDisplayName, Browser, OS, FullLocation
| mvexpand TimeGenerated, IPAddresses, Status
| extend TimeGenerated = todatetime(tostring(TimeGenerated)), IPAddress = tostring(IPAddresses), Status = tostring(Status)
| project-away IPAddresses
| summarize StartTime = min(TimeGenerated), EndTime = max(TimeGenerated) by UserPrincipalName, UserId, UserDisplayName, Status, FailedLogonCount, IPAddress, IPAddressCount, AppDisplayName, Browser, OS, FullLocation
| where (IPAddressCount >= threshold_IPAddressCount and FailedLogonCount >= threshold_Failed) or FailedLogonCount >= threshold_FailedwithSingleIP
| project UserPrincipalName);
OfficeActivity
| where TimeGenerated > ago(time_window)
| where Operation =~ "MemberRoleChanged"
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
| where Role == '2'
| where Members in (failed_signins)
```

Asimismo, puede hacer que las detecciones de SigninLogs sean específicas para Teams agregando un filtro solo para los inicios de sesión basados en Teams mediante:

```Kusto
| where AppDisplayName has 'Teams'
```

Para explicar mejor el uso de *donde AppDisplayName tiene Teams*, el KQL que se muestra a continuación muestra un inicio de sesión correcto de una dirección IP con un error de una dirección IP diferente, pero con un ámbito de *solo* los inicios de sesión de Teams:

```Kusto
let timeFrame = 1d;
let logonDiff = 10m;
SigninLogs 
  | where TimeGenerated >= ago(timeFrame) 
  | where ResultType == "0" 
  | where AppDisplayName has "Teams"
  | project SuccessLogonTime = TimeGenerated, UserPrincipalName, SuccessIPAddress = IPAddress, AppDisplayName, SuccessIPBlock = strcat(split(IPAddress, ".")[0], ".", split(IPAddress, ".")[1])
  | join kind= inner (
      SigninLogs 
      | where TimeGenerated >= ago(timeFrame) 
      | where ResultType !in ("0", "50140") 
      | where ResultDescription !~ "Other"  
      | where AppDisplayName startswith "Microsoft Teams"
      | project FailedLogonTime = TimeGenerated, UserPrincipalName, FailedIPAddress = IPAddress, AppDisplayName, ResultType, ResultDescription
  ) on UserPrincipalName, AppDisplayName 
  | where SuccessLogonTime < FailedLogonTime and FailedLogonTime - SuccessLogonTime <= logonDiff and FailedIPAddress !startswith SuccessIPBlock
  | summarize FailedLogonTime = max(FailedLogonTime), SuccessLogonTime = max(SuccessLogonTime) by UserPrincipalName, SuccessIPAddress, AppDisplayName, FailedIPAddress, ResultType, ResultDescription 
  | extend timestamp = SuccessLogonTime, AccountCustomEntity = UserPrincipalName, IPCustomEntity = SuccessIPAddress
```

## <a name="important-information-and-updates"></a>Información y actualizaciones importantes

**Gracias por colaborar en el contenido, Pedro Bryan, Nicholas DiCola y Matthew Gómez.** Pete Bryan y las personas con las que colabora siguen desarrollando consultas de detección y búsqueda para Teams.

Mantenga el contacto con este repositorio de [Git Hub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) para obtener actualizaciones.

Esté atento para las actualizaciones del [analizador](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) y la [aplicación lógica](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) usados en este artículo.

También debería unirse a la [comunidad de Azure Sentinel](https://github.com/Azure/Azure-Sentinel/wiki) y colaborar en ella. Estamos buscando activamente comentarios sobre este artículo, así que use la siguiente opción de comentarios. Gracias y feliz búsqueda.

[Registro de la aplicación en Azure AD](/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0).

[Activar o desactivar la búsqueda de registros de auditoría](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)

[¿Qué es Azure Sentinel?](/azure/sentinel/overview)
