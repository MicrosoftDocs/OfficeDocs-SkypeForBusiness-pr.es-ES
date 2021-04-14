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
# <a name="azure-sentinel-and-microsoft-teams"></a><span data-ttu-id="82d7b-103">Azure Sentinel y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="82d7b-103">Azure Sentinel and Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="82d7b-104">Azure Sentinel ahora tiene un conector integrado.</span><span class="sxs-lookup"><span data-stu-id="82d7b-104">Azure Sentinel now has an integrated connector.</span></span> <span data-ttu-id="82d7b-105">Para obtener más información, consulte [Conectar los registros de Office 365 a Azure Sentinel](/azure/sentinel/connect-office-365).</span><span class="sxs-lookup"><span data-stu-id="82d7b-105">For more information, see [Connect Office 365 Logs to Azure Sentinel](/azure/sentinel/connect-office-365).</span></span> <span data-ttu-id="82d7b-106">Esta es la ruta recomendada para recopilar estos registros y sustituye los métodos de recopilación que se describen a continuación.</span><span class="sxs-lookup"><span data-stu-id="82d7b-106">This is the recommended route for collecting these logs and supersedes the collection methods described below.</span></span>

<span data-ttu-id="82d7b-107">Teams desempeña un papel fundamental en la comunicación y en el uso compartido de datos en la nube de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="82d7b-107">Teams serves a central role in communication and data-sharing in the Microsoft 365 Cloud.</span></span> <span data-ttu-id="82d7b-108">Dado que Teams toca tantas tecnologías en la nube, puede beneficiarse de análisis humanos y automatizados.</span><span class="sxs-lookup"><span data-stu-id="82d7b-108">Since Teams touches on so many technologies in the Cloud, it can benefit from human and automated analysis.</span></span> <span data-ttu-id="82d7b-109">Esto se aplica tanto a la *búsqueda en registros* como a la *supervisión de reuniones en tiempo real*.</span><span class="sxs-lookup"><span data-stu-id="82d7b-109">This applies to both *hunting in logs*, and *real-time monitoring of meetings*.</span></span> <span data-ttu-id="82d7b-110">Estas soluciones las proporcionan los administradores de Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="82d7b-110">Azure Sentinel offers admins these solutions.</span></span>

> [!NOTE]
> <span data-ttu-id="82d7b-111">¿Necesita un actualizador de Azure Sentinel?</span><span class="sxs-lookup"><span data-stu-id="82d7b-111">Need a refresher on Azure Sentinel?</span></span> <span data-ttu-id="82d7b-112">[Este artículo](/azure/sentinel/overview) es la solución..</span><span class="sxs-lookup"><span data-stu-id="82d7b-112">[This article](/azure/sentinel/overview) is just the thing.</span></span>

## <a name="sentinel-and-microsoft-teams-activity-logs"></a><span data-ttu-id="82d7b-113">Registros de actividad de Sentinel y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="82d7b-113">Sentinel and Microsoft Teams Activity Logs</span></span>

<span data-ttu-id="82d7b-114">El presente artículo se centra en la recopilación de los registros de actividad de los equipos en Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="82d7b-114">This article focuses on collecting Teams activity logs in Azure Sentinel.</span></span>

<span data-ttu-id="82d7b-115">Sentinel permite a los administradores realizar la gestión de la seguridad en un solo lugar.</span><span class="sxs-lookup"><span data-stu-id="82d7b-115">Sentinel lets administrators do security management in one location.</span></span> <span data-ttu-id="82d7b-116">Esto incluye administrar:</span><span class="sxs-lookup"><span data-stu-id="82d7b-116">This includes managing:</span></span>

- <span data-ttu-id="82d7b-117">Dispositivos de terceros</span><span class="sxs-lookup"><span data-stu-id="82d7b-117">Third-party devices</span></span>
- <span data-ttu-id="82d7b-118">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="82d7b-118">Microsoft Threat Protection</span></span>
- <span data-ttu-id="82d7b-119">Cargas de trabajo de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="82d7b-119">Microsoft 365 Workloads</span></span>

<span data-ttu-id="82d7b-120">Los libros de trabajo y runbooks de Sentinel pueden hacer que la supervisión de la seguridad sea *sistemática*.</span><span class="sxs-lookup"><span data-stu-id="82d7b-120">Sentinel workbooks and runbooks can make security monitoring *systematic*.</span></span> <span data-ttu-id="82d7b-121">Un buen primer paso en este proceso es recopilar los registros necesarios para el análisis.</span><span class="sxs-lookup"><span data-stu-id="82d7b-121">A good first step in this process is collecting the logs needed analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="82d7b-122">Puede aparecer más de una suscripción a Microsoft 365 en la misma instancia de Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="82d7b-122">More than one Microsoft 365 subscription can be surfaced in the same instance of Azure Sentinel.</span></span> <span data-ttu-id="82d7b-123">Esto permite la supervisión [en tiempo real](/azure/sentinel/livestream) y la búsqueda de amenazas en los archivos de registro históricos.</span><span class="sxs-lookup"><span data-stu-id="82d7b-123">This will allow for [realtime monitoring](/azure/sentinel/livestream) and hunting for threats in historical log files.</span></span> <span data-ttu-id="82d7b-124">Los administradores podrán realizar búsquedas mediante [consultas entre recursos](/azure/azure-monitor/log-query/cross-workspace-query), es decir, dentro de un solo grupo de recursos, entre grupos de recursos o en otra suscripción.  </span><span class="sxs-lookup"><span data-stu-id="82d7b-124">Administrators will be able to hunt using [cross-resource queries](/azure/azure-monitor/log-query/cross-workspace-query), that is within a single resource group, across resource groups, or in another subscription.</span></span>

## <a name="step-1-collect-teams-logs-enable-audit-logs-in-microsoft-365"></a><span data-ttu-id="82d7b-125">Paso 1: Recopilar registros de Microsoft Teams: Habilitar registros de auditoría en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="82d7b-125">Step 1: Collect Teams logs: Enable Audit logs in Microsoft 365</span></span>

<span data-ttu-id="82d7b-126">Dado que Teams registra la actividad a través de Microsoft 365, los registros de auditoría no se recopilan de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="82d7b-126">Because Teams logs activity through Microsoft 365, audit logs aren't collected by default.</span></span> <span data-ttu-id="82d7b-127">Active esta característica con [estos pasos](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span><span class="sxs-lookup"><span data-stu-id="82d7b-127">Turn on this feature with [these steps](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span></span> <span data-ttu-id="82d7b-128">Los datos de Microsoft Teams se recopilan en la auditoría de Microsoft 365, en *Audit.General*.</span><span class="sxs-lookup"><span data-stu-id="82d7b-128">Teams data is collected in the Microsoft 365 audit under *Audit.General*.</span></span>

## <a name="step-2-connect-office-365-logs-to-azure-sentinel"></a><span data-ttu-id="82d7b-129">Paso 2: Conectar los registros de Office 365 a Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="82d7b-129">Step 2: Connect Office 365 logs to Azure Sentinel</span></span>

<span data-ttu-id="82d7b-130">Azure Sentinel proporciona un conector integrado para los registros de Office 365, que le permite incorporar datos de Teams en Azure Sentinel junto con otros datos de Office 365.</span><span class="sxs-lookup"><span data-stu-id="82d7b-130">Azure Sentinel provides a built-in connector for Office 365 logs, which enables you to ingest Teams data into Azure Sentinel together with other Office 365 data.</span></span>
 
<span data-ttu-id="82d7b-131">En Azure Sentinel, habilite el conector de datos de Office 365.</span><span class="sxs-lookup"><span data-stu-id="82d7b-131">In Azure Sentinel, enable the Office 365 data connector.</span></span> <span data-ttu-id="82d7b-132">Para más información, consulte la [documentación de Azure Sentinel](/azure/sentinel/connect-office-365).</span><span class="sxs-lookup"><span data-stu-id="82d7b-132">For more information, see the [Azure Sentinel documentation](/azure/sentinel/connect-office-365).</span></span>

## <a name="helpful-hunting-kql-queries"></a><span data-ttu-id="82d7b-133">Consultas útiles de búsqueda de KQL</span><span class="sxs-lookup"><span data-stu-id="82d7b-133">Helpful hunting KQL queries</span></span>

<span data-ttu-id="82d7b-134">Use estas consultas para familiarizarse con el entorno de equipos y datos de su equipo.</span><span class="sxs-lookup"><span data-stu-id="82d7b-134">Use these queries to familiarize yourself with your Teams data and Teams environment.</span></span> <span data-ttu-id="82d7b-135">El conocer cómo debe verse y comportarse el entorno es un excelente primer paso para reconocer una actividad sospechosa.</span><span class="sxs-lookup"><span data-stu-id="82d7b-135">Knowing how the environment should look and behave is a good first step in recognizing suspicious activity.</span></span> <span data-ttu-id="82d7b-136">Desde allí, puede llegar a la búsqueda de amenazas.</span><span class="sxs-lookup"><span data-stu-id="82d7b-136">From there, you can branch out into threat hunting.</span></span>

### <a name="federated-external-users-query"></a><span data-ttu-id="82d7b-137">Consulta de usuarios externos federados</span><span class="sxs-lookup"><span data-stu-id="82d7b-137">Federated external users query</span></span>

<span data-ttu-id="82d7b-138">Obtenga una lista de los sitios de Teams que tienen usuarios externos federados.</span><span class="sxs-lookup"><span data-stu-id="82d7b-138">Get the list of Teams sites that have federated external users.</span></span> <span data-ttu-id="82d7b-139">Estos usuarios tienen un sufijo de UPN y/o nombre de dominio que no pertenece a su organización.</span><span class="sxs-lookup"><span data-stu-id="82d7b-139">These users have a domain name and/or a UPN suffix that isn't owned by your organization.</span></span>

<span data-ttu-id="82d7b-140">En esta consulta de ejemplo, la organización es propietaria de contoso.com.</span><span class="sxs-lookup"><span data-stu-id="82d7b-140">In this example query, the organization owns contoso.com.</span></span>

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
> <span data-ttu-id="82d7b-141">Para más información sobre los tipos de acceso de invitado y externo en Teams, consulte [Comunicarse con usuarios de otras organizaciones](communicate-with-users-from-other-organizations.md) o la sección [Tipos de participante](teams-security-guide.md#participant-types) en la Guía de seguridad de Teams.</span><span class="sxs-lookup"><span data-stu-id="82d7b-141">To learn more about External and Guest access types in Teams see [Communicate with users from other organizations](communicate-with-users-from-other-organizations.md), or the [Participant Types](teams-security-guide.md#participant-types) section in the Teams Security Guide.</span></span>

### <a name="who-recently-joined--whose-role-changed"></a><span data-ttu-id="82d7b-142">Quién se unió recientemente o cambió su rol</span><span class="sxs-lookup"><span data-stu-id="82d7b-142">Who recently joined / Whose role changed</span></span>

<span data-ttu-id="82d7b-143">Consulte a un usuario específico para comprobar si se han agregado a un canal de Teams en los últimos siete días, o en una semana:</span><span class="sxs-lookup"><span data-stu-id="82d7b-143">Query a specific user to check if they were added to a Teams channel in the last seven days, or within a week:</span></span>

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members has "<DisplayName>" or Members has "<UserPrincipalName>"
| project TeamName, Operation, UserId, Members
```

<span data-ttu-id="82d7b-144">Consulte si el rol de un usuario cambió para un equipo en los últimos siete días:</span><span class="sxs-lookup"><span data-stu-id="82d7b-144">Query whether a user's role changed for a Team in the last seven days:</span></span>

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| project TeamName, Operation, UserId, Members
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
| where Role == '1'
``` 

### <a name="external-users-from-unknown-or-new-organizations"></a><span data-ttu-id="82d7b-145">Usuarios externos de organizaciones desconocidas o nuevas</span><span class="sxs-lookup"><span data-stu-id="82d7b-145">External users from unknown or new organizations</span></span>

<span data-ttu-id="82d7b-146">En Teams, puede agregar usuarios externos a su entorno o canales.</span><span class="sxs-lookup"><span data-stu-id="82d7b-146">In Teams, you can add external users to your environment or channels.</span></span> <span data-ttu-id="82d7b-147">Las organizaciones suelen tener un número limitado de asociaciones clave y agregar usuarios de entre estos asociados.</span><span class="sxs-lookup"><span data-stu-id="82d7b-147">Organizations often have a limited number of key partnerships and add users from among these partners.</span></span> <span data-ttu-id="82d7b-148">Esta KQL se ocupa de los usuarios externos añadidos a los equipos que provienen de organizaciones que no han sido vistas o añadidas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="82d7b-148">This KQL looks at external users added to teams who come from organizations that haven't been seen or added before.</span></span>

<span data-ttu-id="82d7b-149">Para más información, vea la consulta en el [centro de git de la comunidad de Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/ExternalUserFromNewOrgAddedToTeams.yaml).</span><span class="sxs-lookup"><span data-stu-id="82d7b-149">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/ExternalUserFromNewOrgAddedToTeams.yaml).</span></span>

### <a name="external-users-who-were-added-and-then-removed"></a><span data-ttu-id="82d7b-150">Usuarios externos que se añadieron y que luego fueron eliminados </span><span class="sxs-lookup"><span data-stu-id="82d7b-150">External users who were added and then removed</span></span>

<span data-ttu-id="82d7b-151">Los atacantes con algún nivel de acceso existente pueden agregar una nueva cuenta externa a los Teams para tener acceso a los datos y exfiltrarlos.</span><span class="sxs-lookup"><span data-stu-id="82d7b-151">Attackers with some level of existing access may add a new external account to Teams to access and exfiltrate data.</span></span> <span data-ttu-id="82d7b-152">También pueden quitar rápidamente a ese usuario para ocultar que ha realizado el acceso.</span><span class="sxs-lookup"><span data-stu-id="82d7b-152">They may also quickly remove that user to hide that they made access.</span></span> <span data-ttu-id="82d7b-153">Esta búsqueda busca cuentas externas que se agregan a Teams y se quitan rápidamente para ayudar a identificar comportamientos sospechosos.</span><span class="sxs-lookup"><span data-stu-id="82d7b-153">This query hunts for external accounts that are added to Teams and swiftly removed to help identify suspicious behavior.</span></span>

<span data-ttu-id="82d7b-154">Para más información, vea la consulta en el [centro de git de la comunidad de Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Detections/OfficeActivity/ExternalUserAddedRemovedInTeams.yaml).</span><span class="sxs-lookup"><span data-stu-id="82d7b-154">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Detections/OfficeActivity/ExternalUserAddedRemovedInTeams.yaml).</span></span>

### <a name="new-bot-or-application-added"></a><span data-ttu-id="82d7b-155">Se agregó un nuevo bot o aplicación</span><span class="sxs-lookup"><span data-stu-id="82d7b-155">New bot or application added</span></span>

<span data-ttu-id="82d7b-156">Microsoft Teams puede incluir aplicaciones o bots en un equipo para ampliar el conjunto de características (incluidas aplicaciones personalizadas y bots).</span><span class="sxs-lookup"><span data-stu-id="82d7b-156">Teams can include apps or bots in a Team to extend the feature set (including custom apps and bots).</span></span> <span data-ttu-id="82d7b-157">En algunos casos, se puede usar una aplicación o bot para *la persistencia* en Teams sin necesidad de una cuenta de usuario y se puede obtener acceso a archivos y otros datos.</span><span class="sxs-lookup"><span data-stu-id="82d7b-157">In some cases, an app or bot can be used for *persistence* in Teams without needing a user account, and can access files and other data.</span></span> <span data-ttu-id="82d7b-158">Esta consulta busca aplicaciones o bots que son nuevos para Teams. </span><span class="sxs-lookup"><span data-stu-id="82d7b-158">This query hunts for apps or bots that are new to Teams.</span></span>

<span data-ttu-id="82d7b-159">Para más información, vea la consulta en el [centro de git de la comunidad de Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/NewBotAddedToTeams.yaml).</span><span class="sxs-lookup"><span data-stu-id="82d7b-159">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/NewBotAddedToTeams.yaml).</span></span>

### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a><span data-ttu-id="82d7b-160">Cuentas de usuario que son propietarios de un gran número de equipos  </span><span class="sxs-lookup"><span data-stu-id="82d7b-160">User accounts who are Owners of large numbers of Teams</span></span>

<span data-ttu-id="82d7b-161">Los atacantes que buscan elevar sus privilegios pueden asignarse a sí mismos privilegios de propietario de un gran número de equipos diversos.</span><span class="sxs-lookup"><span data-stu-id="82d7b-161">Attackers looking to elevate their privileges may assign themselves Owner privileges of a large number of diverse teams.</span></span> <span data-ttu-id="82d7b-162">*Normalmente*, los usuarios crean y poseen algunos equipos sobre temas específicos.</span><span class="sxs-lookup"><span data-stu-id="82d7b-162">*Usually*, users create and own a few teams around specific topics.</span></span> <span data-ttu-id="82d7b-163">Esta consulta de KQL busca comportamientos sospechosos.</span><span class="sxs-lookup"><span data-stu-id="82d7b-163">This KQL query looks for suspicious behavior.</span></span>

<span data-ttu-id="82d7b-164">Para más información, vea la consulta en el [centro de git de la comunidad de Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultiTeamOwner.yaml).</span><span class="sxs-lookup"><span data-stu-id="82d7b-164">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultiTeamOwner.yaml).</span></span>

### <a name="many-team-deletions-by-a-single-user"></a><span data-ttu-id="82d7b-165">Muchas eliminaciones de equipo de un único usuario</span><span class="sxs-lookup"><span data-stu-id="82d7b-165">Many Team deletions by a single user</span></span>

<span data-ttu-id="82d7b-166">Los atacantes pueden causar interrupciones y perjudicar proyectos y datos eliminando varios equipos.</span><span class="sxs-lookup"><span data-stu-id="82d7b-166">Attackers can cause disruptions and jeopardize projects and data by deleting multiple teams.</span></span> <span data-ttu-id="82d7b-167">Dado que los equipos suelen ser eliminados por propietarios individuales, la eliminación centralizada de muchos equipos puede ser una señal de problemas.</span><span class="sxs-lookup"><span data-stu-id="82d7b-167">Since teams are usually deleted by individual Owners, central deletion of many teams can be a sign of trouble.</span></span> <span data-ttu-id="82d7b-168">Esta KQL busca usuarios únicos que eliminan varios equipos.</span><span class="sxs-lookup"><span data-stu-id="82d7b-168">This KQL looks for single users who delete multiple teams.</span></span>

<span data-ttu-id="82d7b-169">Para más información, vea la consulta en el [centro de git de la comunidad de Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultipleTeamsDeletes.yaml).</span><span class="sxs-lookup"><span data-stu-id="82d7b-169">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultipleTeamsDeletes.yaml).</span></span>

### <a name="expanding-your-threat-hunting-opportunities"></a><span data-ttu-id="82d7b-170">Ampliar las oportunidades de búsqueda de amenazas</span><span class="sxs-lookup"><span data-stu-id="82d7b-170">Expanding your threat hunting opportunities</span></span>

<span data-ttu-id="82d7b-171">La combinación de consultas de recursos como Azure Active Directory (Azure AD) u otras cargas de trabajo de Office 365 puede usarse con consultas de Teams.</span><span class="sxs-lookup"><span data-stu-id="82d7b-171">Combining queries from resources like Azure Active Directory (Azure AD), or other Office 365 workloads can be used with Teams queries.</span></span> <span data-ttu-id="82d7b-172">Por ejemplo, combine la detección de patrones sospechosos en SigninLogs de Azure AD y use ese resultado mientras busca propietarios del equipo.</span><span class="sxs-lookup"><span data-stu-id="82d7b-172">For example, combine the detection of suspicious patterns in Azure AD SigninLogs, and use that output while hunting for Team Owners.</span></span>

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

<span data-ttu-id="82d7b-173">Asimismo, puede hacer que las detecciones de SigninLogs sean específicas para Teams agregando un filtro solo para los inicios de sesión basados en Teams mediante:</span><span class="sxs-lookup"><span data-stu-id="82d7b-173">Also, you can make the SigninLogs detections specific to Teams by adding a filter for only Teams-based logons by using:</span></span>

```Kusto
| where AppDisplayName has 'Teams'
```

<span data-ttu-id="82d7b-174">Para explicar mejor el uso de *donde AppDisplayName tiene Teams*, el KQL que se muestra a continuación muestra un inicio de sesión correcto de una dirección IP con un error de una dirección IP diferente, pero con un ámbito de *solo* los inicios de sesión de Teams:</span><span class="sxs-lookup"><span data-stu-id="82d7b-174">To help explain using *where AppDisplayName has Teams* further, the KQL you see below demonstrates a successful logon from one IP address with failure from a different IP address, but scoped to *only* Teams sign-ins:</span></span>

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

## <a name="important-information-and-updates"></a><span data-ttu-id="82d7b-175">Información y actualizaciones importantes</span><span class="sxs-lookup"><span data-stu-id="82d7b-175">Important information and updates</span></span>

<span data-ttu-id="82d7b-176">**Gracias por colaborar en el contenido, Pedro Bryan, Nicholas DiCola y Matthew Gómez.**</span><span class="sxs-lookup"><span data-stu-id="82d7b-176">**Thank you for content collaboration, Pete Bryan, Nicholas DiCola, and Matthew Lowe.**</span></span> <span data-ttu-id="82d7b-177">Pete Bryan y las personas con las que colabora siguen desarrollando consultas de detección y búsqueda para Teams.</span><span class="sxs-lookup"><span data-stu-id="82d7b-177">Pete Bryan, and people he collaborates with, continue to develop detection and hunting queries for Teams.</span></span>

<span data-ttu-id="82d7b-178">Mantenga el contacto con este repositorio de [Git Hub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) para obtener actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="82d7b-178">Stay in touch with this [Git Hub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) repository for updates.</span></span>

<span data-ttu-id="82d7b-179">Esté atento para las actualizaciones del [analizador](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) y la [aplicación lógica](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) usados en este artículo.</span><span class="sxs-lookup"><span data-stu-id="82d7b-179">Watch for updates to the [parser](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) and [logic app](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) used in this article.</span></span>

<span data-ttu-id="82d7b-180">También debería unirse a la [comunidad de Azure Sentinel](https://github.com/Azure/Azure-Sentinel/wiki) y colaborar en ella.</span><span class="sxs-lookup"><span data-stu-id="82d7b-180">You should also join (and contribute to) the [Azure Sentinel community](https://github.com/Azure/Azure-Sentinel/wiki).</span></span> <span data-ttu-id="82d7b-181">Estamos buscando activamente comentarios sobre este artículo, así que use la siguiente opción de comentarios.</span><span class="sxs-lookup"><span data-stu-id="82d7b-181">We are actively looking for feedback on this article, so please use the feedback option below.</span></span> <span data-ttu-id="82d7b-182">Gracias y feliz búsqueda.</span><span class="sxs-lookup"><span data-stu-id="82d7b-182">Thank you & Happy hunting.</span></span>

<span data-ttu-id="82d7b-183">[Registro de la aplicación en Azure AD](/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0).</span><span class="sxs-lookup"><span data-stu-id="82d7b-183">[Registering your application in Azure AD](/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0)</span></span>

[<span data-ttu-id="82d7b-184">Activar o desactivar la búsqueda de registros de auditoría</span><span class="sxs-lookup"><span data-stu-id="82d7b-184">Turn audit log search on or off</span></span>](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)

[<span data-ttu-id="82d7b-185">¿Qué es Azure Sentinel?</span><span class="sxs-lookup"><span data-stu-id="82d7b-185">What is Azure Sentinel?</span></span>](/azure/sentinel/overview)
