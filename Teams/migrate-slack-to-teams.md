---
title: Migración de Slack a Microsoft Teams
author: lolajacobsen
ms.author: lolaj
ms.reviewer: brandber
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1.keywords:
- NOCSH
description: Instrucciones detalladas para migrar de Slack a Microsoft Teams.
ms.openlocfilehash: ca104baf5baebaa0e44c2202794c1b8ed6862633
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638649"
---
# <a name="migrate-from-slack-to-microsoft-teams"></a><span data-ttu-id="59ba4-103">Migración de Slack a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="59ba4-103">Migrate from Slack to Microsoft Teams</span></span>

<span data-ttu-id="59ba4-104">Este artículo le guiará en el proceso para migrar a Microsoft Teams desde Slack.</span><span class="sxs-lookup"><span data-stu-id="59ba4-104">This article walks you through the journey of moving to Microsoft Teams from Slack.</span></span>

<span data-ttu-id="59ba4-105">Al planear la migración de los equipos de la organización a un equipo, es importante que decida qué debe mantenerse (si es que es necesario).</span><span class="sxs-lookup"><span data-stu-id="59ba4-105">When planning your organization’s move to Teams from Slack, it's important to decide what you need to keep (if anything).</span></span> <span data-ttu-id="59ba4-106">Empezaremos por describir qué tipos de datos se pueden migrar y, después, explicaremos cómo evaluar sus necesidades, planear la migración y completar la misma.</span><span class="sxs-lookup"><span data-stu-id="59ba4-106">We'll start off by describing what types of data can be migrated and then walk you through how to assess your needs, plan your move, and then make the move.</span></span>

<span data-ttu-id="59ba4-107">El diagrama siguiente muestra la arquitectura de Slack a nivel general.</span><span class="sxs-lookup"><span data-stu-id="59ba4-107">The diagram below shows the Slack architecture at a high level.</span></span>

![Imagen que muestra la arquitectura de Slack a nivel general](media/migrate-slack-to-teams-image1.png)

## <a name="plan-your-migration-from-slack"></a><span data-ttu-id="59ba4-109">Planear la migración desde Slack</span><span class="sxs-lookup"><span data-stu-id="59ba4-109">Plan your migration from Slack</span></span>
### <a name="what-you-can-and-cant-migrate"></a><span data-ttu-id="59ba4-110">Qué puede y qué no puede migrar</span><span class="sxs-lookup"><span data-stu-id="59ba4-110">What you can and can’t migrate</span></span>
<span data-ttu-id="59ba4-111">Su plan de servicio de Slack determinará qué es lo que puede y no puede migrar.</span><span class="sxs-lookup"><span data-stu-id="59ba4-111">Your Slack service plan will determine what you can and can’t migrate.</span></span> <span data-ttu-id="59ba4-112">Por ejemplo, algunos planes de servicio de Slack solo permiten exportar los archivos y el historial de canales públicos, mientras que otros requieren una solicitud DocuSign para incluir canales privados y mensajes directos.</span><span class="sxs-lookup"><span data-stu-id="59ba4-112">For example, some Slack service plans only let you export public channels history and files, other require a DocuSign request to include Private Channels and Direct Messages.</span></span> 

<span data-ttu-id="59ba4-113">Para determinar el nivel de servicio del área de trabajo de Slack, inicie sesión en Slack y anote el tipo de plan que aparece en la página **Acerca de este espacio de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="59ba4-113">To determine your Slack Workspace service level, log into Slack and note your plan type on the **About this Workspace** page.</span></span>

<span data-ttu-id="59ba4-114">Para más información sobre las opciones de exportación de Slack, vaya al sitio web de Slack: https://get.slack.help/hc/articles/204897248-Guide-to-Slack-import-and-export-tools</span><span class="sxs-lookup"><span data-stu-id="59ba4-114">To learn more about Slack export options, go to the Slack website: https://get.slack.help/hc/articles/204897248-Guide-to-Slack-import-and-export-tools</span></span> 

<span data-ttu-id="59ba4-115">El siguiente diagrama muestra una visión general del panorama de migración de Slack que trataremos en este artículo.</span><span class="sxs-lookup"><span data-stu-id="59ba4-115">The diagram below gives you a high-level look at the Slack migration landscape that we’ll cover in this article.</span></span> 

![Diagrama en el que se muestra el panorama de exportación de Slack.](media/migrate-slack-to-teams-image2.png)

<span data-ttu-id="59ba4-117">Cuando haya terminado con esta sección, debería comprender lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="59ba4-117">When you're done with this section, you should understand:</span></span>
- <span data-ttu-id="59ba4-118">El nivel de servicio de sus áreas de trabajo de Slack.</span><span class="sxs-lookup"><span data-stu-id="59ba4-118">The service level of your Slack Workspaces</span></span>
- <span data-ttu-id="59ba4-119">Lo que puede y no puede exportar.</span><span class="sxs-lookup"><span data-stu-id="59ba4-119">What can and can't be exported</span></span>
- <span data-ttu-id="59ba4-120">Métodos comunes para la exportación.</span><span class="sxs-lookup"><span data-stu-id="59ba4-120">Common approaches to exporting</span></span>

### <a name="assess-your-slack-workspaces"></a><span data-ttu-id="59ba4-121">Evaluación de los espacios de trabajo de Slack</span><span class="sxs-lookup"><span data-stu-id="59ba4-121">Assess your Slack workspaces</span></span>
<span data-ttu-id="59ba4-122">Para poder planear el plan de migración de su organización, debe reunir cierta información sobre sus áreas de trabajo de Slack.</span><span class="sxs-lookup"><span data-stu-id="59ba4-122">Before you can plan your organization’s migration plan, you need to pull together some information about your Slack workspaces.</span></span> <span data-ttu-id="59ba4-123">Entender cómo se usan las áreas de trabajo de Slack le ayuda a determinar el alcance de la migración.</span><span class="sxs-lookup"><span data-stu-id="59ba4-123">Understanding how your Slack workspaces are being used helps you determine the scope of your migration.</span></span> <span data-ttu-id="59ba4-124">Por ejemplo, ¿cuántas áreas de trabajo se van a migrar?</span><span class="sxs-lookup"><span data-stu-id="59ba4-124">For example, how many workspaces are being moved?</span></span> <span data-ttu-id="59ba4-125">¿Los usan en un departamento específico, muchos departamentos o una organización entera?</span><span class="sxs-lookup"><span data-stu-id="59ba4-125">Are they used by a specific department, many, or in use by an entire organization?</span></span>

<span data-ttu-id="59ba4-126">Si es miembro de las áreas de trabajo de Slack que quiere migrar, puede analizar el uso yendo a *<your Slack workspace>.slack.com/stats*. Revise las pestañas Canales y Miembros para buscar patrones de uso.</span><span class="sxs-lookup"><span data-stu-id="59ba4-126">If you’re a member of the Slack Workspaces you want to migrate, you can analyze the usage yourself by going to *<your Slack workspace>.slack.com/stats*. Review the Channels and Members tabs to look for usage patterns.</span></span> <span data-ttu-id="59ba4-127">Decida las áreas de trabajo que quiere migrar (y cuáles son las que dejará de utilizar).</span><span class="sxs-lookup"><span data-stu-id="59ba4-127">Decide which workspaces you want to migrate (and which ones you want to leave behind).</span></span> 

> [!NOTE]
> <span data-ttu-id="59ba4-128">Si no tiene acceso a la página de estadísticas, no es un administrador o propietario.</span><span class="sxs-lookup"><span data-stu-id="59ba4-128">If you don’t have access to the stats page, you’re not an admin or owner.</span></span> 

### <a name="export-channels"></a><span data-ttu-id="59ba4-129">Exportación de canales</span><span class="sxs-lookup"><span data-stu-id="59ba4-129">Export Channels</span></span>

<span data-ttu-id="59ba4-130">En Slack, los usuarios se unen a un canal que forma parte de un área de trabajo de Slack, mientras que en Teams los usuarios se unen a equipos, que son colecciones de canales.</span><span class="sxs-lookup"><span data-stu-id="59ba4-130">In Slack, users join a channel which is part of a Slack Workspace, whereas in Teams users join a team which is a collection of channels.</span></span> <span data-ttu-id="59ba4-131">Le recomendamos que use los datos de análisis de Slack para ver cuánta actividad tiene lugar en cada canal y así decidir qué canales migrar.</span><span class="sxs-lookup"><span data-stu-id="59ba4-131">We recommend that you use Slack analytics to see how much activity happens in each channel to help you decide which channels to move.</span></span> <span data-ttu-id="59ba4-132">Use la lista resultante para averiguar cómo agrupar los canales de Slack en los equipos de Teams, así como quién debe ser miembro de cada equipo.</span><span class="sxs-lookup"><span data-stu-id="59ba4-132">You’ll use the resulting list to figure out how to group your Slack channels into teams in Teams as well as who should be members of each team.</span></span>

<span data-ttu-id="59ba4-133">Si tiene un plan de servicio de pago de Slack (que no sea gratuito), puede usar los datos de análisis de Slack (<your Slack workspace>.slack.com/admin/stats#channels) para ver el nivel de actividad de un canal, cuándo se utilizó por última vez y cuántos usuarios son miembros.</span><span class="sxs-lookup"><span data-stu-id="59ba4-133">If you have a paid Slack service plan (anything other than Free), you can use Slack’s analytics (<your Slack workspace>.slack.com/admin/stats#channels) to see how active a channel is, when it was last used, and how many people are members.</span></span> <span data-ttu-id="59ba4-134">Esto puede ayudarle a decidir si quiere migrar el canal.</span><span class="sxs-lookup"><span data-stu-id="59ba4-134">This can help you decide whether to migrate the channel.</span></span> <span data-ttu-id="59ba4-135">De forma predeterminada, se puede exportar el contenido de canales públicos (archivos y mensajes).</span><span class="sxs-lookup"><span data-stu-id="59ba4-135">By default, public channels content (messages and files) can be exported.</span></span> <span data-ttu-id="59ba4-136">En función de su plan de servicio de Slack y de si ha solicitado canales privados y mensajes directos de Slack, estos pueden o no exportarse.</span><span class="sxs-lookup"><span data-stu-id="59ba4-136">Depending on your Slack service plan and whether you’ve requested Private Channels and Direct Messages from Slack, those can be exported.</span></span>

<span data-ttu-id="59ba4-137">Para más información sobre las opciones de exportación de Slack, vaya al sitio web de Slack: https://get.slack.help/hc/articles/204897248-Guide-to-Slack-import-and-export-tools</span><span class="sxs-lookup"><span data-stu-id="59ba4-137">To learn more about Slack export options, go to the Slack website: https://get.slack.help/hc/articles/204897248-Guide-to-Slack-import-and-export-tools</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="59ba4-138">Compruebe los requisitos de privacidad y cumplimiento de su organización respecto a los datos de los canales.</span><span class="sxs-lookup"><span data-stu-id="59ba4-138">Check your organization’s privacy and compliance requirements around channel data.</span></span> <span data-ttu-id="59ba4-139">Es posible que su organización tenga requisitos de cumplimiento sobre el tratamiento, almacenamiento y procesamiento de estos datos, además de cumplir con el ciclo de vida de contenido identificable del usuario final (EUII).</span><span class="sxs-lookup"><span data-stu-id="59ba4-139">Your organization may have compliance requirements around the handling, storage, and processing of this data, in addition to complying with the lifecycle of end-user identifiable content (EUII).</span></span>

### <a name="export-direct-messages"></a><span data-ttu-id="59ba4-140">Exportación de mensajes directos</span><span class="sxs-lookup"><span data-stu-id="59ba4-140">Export Direct Messages</span></span>
<span data-ttu-id="59ba4-141">Los mensajes directos son lo mismo que los chats en Teams, que son conversaciones de uno a uno o de uno a varios que no pertenecen a un canal.</span><span class="sxs-lookup"><span data-stu-id="59ba4-141">Direct Messages are the same as chats in Teams, which are 1:1 or 1-to-many non-channel conversations.</span></span> <span data-ttu-id="59ba4-142">La capacidad de exportación depende del plan de servicio de Slack y de si ha solicitado que se incluyan mensajes directos en la exportación de Slack.</span><span class="sxs-lookup"><span data-stu-id="59ba4-142">Export-ability depends on your Slack service plan and if you’ve requested Direct Messages to be included in your Slack Export.</span></span> <span data-ttu-id="59ba4-143">Teams no es compatible con la importación de mensajes directos en este momento.</span><span class="sxs-lookup"><span data-stu-id="59ba4-143">Teams doesn’t support importing Direct messages currently.</span></span> <span data-ttu-id="59ba4-144">Consulte a un asociado de Microsoft para obtener información sobre las soluciones de terceros que puede explorar y que incorporan el contenido de mensajes directos en Teams.</span><span class="sxs-lookup"><span data-stu-id="59ba4-144">Consult a Microsoft partner to learn about third-party solutions you can explore that bring Direct Messages content into Teams.</span></span>

<span data-ttu-id="59ba4-145">Para exportar mensajes directos, eche un vistazo a herramientas, como Export, en la tienda de aplicaciones de Slack.</span><span class="sxs-lookup"><span data-stu-id="59ba4-145">For exporting Direct Messages, check out tools, such as Export, in the Slack App Store.</span></span>

### <a name="apps-and-custom-integrations"></a><span data-ttu-id="59ba4-146">Aplicaciones e integraciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="59ba4-146">Apps and custom integrations</span></span>

<span data-ttu-id="59ba4-147">Las aplicaciones en Slack son similares a las aplicaciones en Teams.</span><span class="sxs-lookup"><span data-stu-id="59ba4-147">Apps in Slack are like apps in Teams.</span></span> <span data-ttu-id="59ba4-148">Cuando tenga una lista de aplicaciones y sus configuraciones en el área de trabajo, puede buscar en la tienda de aplicaciones de Teams para ver si están disponibles para Teams\*.</span><span class="sxs-lookup"><span data-stu-id="59ba4-148">Once you have a list of apps and their configurations in the Workspace, you can search in the Teams App store to see if they’re available for Teams\*.</span></span> 

<span data-ttu-id="59ba4-149">Vaya a <your Slack workspace>.slack.com/apps/manage para obtener una lista de aplicaciones e integraciones personalizadas.</span><span class="sxs-lookup"><span data-stu-id="59ba4-149">Go to <your Slack workspace>.slack.com/apps/manage to get a list of Apps and Custom Integrations.</span></span> <span data-ttu-id="59ba4-150">En esta página también se muestra el número de configuraciones en que se usa cada aplicación.</span><span class="sxs-lookup"><span data-stu-id="59ba4-150">This page also shows you the number of configurations where each app is in use.</span></span> <span data-ttu-id="59ba4-151">Las integraciones personalizadas pueden variar en su "capacidad de migración".</span><span class="sxs-lookup"><span data-stu-id="59ba4-151">Custom Integrations vary in their “migrate-ability.”</span></span> <span data-ttu-id="59ba4-152">Si es un enlace web, normalmente puede enviarlo a un conector de Microsoft 365 u Office 365 para cambiar el flujo de trabajo a Teams.</span><span class="sxs-lookup"><span data-stu-id="59ba4-152">If it’s a Web Hook, you can usually send it to a Microsoft 365 or Office 365 Connector to shift the workflow into Teams.</span></span> <span data-ttu-id="59ba4-153">Evalúe los bots y otras aplicaciones uno a uno para planear su migración a Teams.</span><span class="sxs-lookup"><span data-stu-id="59ba4-153">Assess bots and other apps on a case-by-case basis to plan for moving them to Teams.</span></span>

<span data-ttu-id="59ba4-154">\* Si el administrador ha restringido el uso de aplicaciones, es posible que no tenga acceso a la lista completa de aplicaciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="59ba4-154">\* If your administrator has restricted apps usage, you may not be looking at the full list of available apps.</span></span>

### <a name="users"></a><span data-ttu-id="59ba4-155">Usuarios</span><span class="sxs-lookup"><span data-stu-id="59ba4-155">Users</span></span>
<span data-ttu-id="59ba4-156">Es posible que los esquemas de identidad que usaba en Slack no se asignen directamente a Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="59ba4-156">The identity schemes you used in Slack might not map directly to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="59ba4-157">Por ejemplo, es posible que las direcciones de correo electrónico de los usuarios de Slack no se asignen a cuentas profesionales o educativas de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="59ba4-157">For example, the email addresses of your Slack users may not map to Microsoft 365 or Office 365 work or school accounts.</span></span> <span data-ttu-id="59ba4-158">Debería crear un mapa de asignación de ID. y usuarios antes de empezar a planear su implementación de Teams.</span><span class="sxs-lookup"><span data-stu-id="59ba4-158">You should create a user-ID map before you start planning your Teams rollout.</span></span>

<span data-ttu-id="59ba4-159">Si tiene un plan de servicio de pago de Slack, puede ir a *<your Slack workspace>.slack.com/admin/stats#members* para obtener información de los miembros, como la dirección de correo electrónico y el tipo de cuenta de cada usuario (por ejemplo, invitado en uno o varios canales).</span><span class="sxs-lookup"><span data-stu-id="59ba4-159">If you’re on a paid Slack service plan, you can go to *<your Slack workspace>.slack.com/admin/stats#members* to get member details such as email address and account type for each user (for example, single vs. multi-channel guest).</span></span>

<span data-ttu-id="59ba4-160">El siguiente es un script que puede usar para comparar las direcciones de correo electrónico de una exportación de Slack con Azure AD para ayudarle a resolver la ambigüedad de nombres.</span><span class="sxs-lookup"><span data-stu-id="59ba4-160">Here’s a script you can use to compare email addresses from a Slack export against Azure AD to help solve for name ambiguity.</span></span> <span data-ttu-id="59ba4-161">También informará de si el usuario está habilitado para Teams.</span><span class="sxs-lookup"><span data-stu-id="59ba4-161">It’ll also report if the user is enabled for Teams.</span></span> <span data-ttu-id="59ba4-162">Si necesita ayuda con PowerShell, consulte [Introducción a Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span><span class="sxs-lookup"><span data-stu-id="59ba4-162">If you need help with PowerShell, read [Get started with Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span></span>

```azurepowershell
Connect-AzureAD
Function Get-TimeStamp {
    return "[{0:MM/dd/yy} {0:HH:mm:ss}]" -f (Get-Date)
}

class User {
    [ValidateNotNullOrEmpty()] $ID
    [ValidateNotNullOrEmpty()] $FullName
    [string] $Email
    [string] $UPN
    [ValidateNotNullOrEmpty()][bool] $ExistsAzureAD
    [ValidateNotNullOrEmpty()][bool] $TeamsEnabled
}

$output = New-Object -type System.Collections.ObjectModel.Collection["User"]

$users = Get-Content -Raw -Path .\slackHistory\users.json | ConvertFrom-Json

Write-Host -ForegroundColor Green "$(Get-Timestamp) User Count: " $users.Count

$i=1
Write-Host "$(Get-Timestamp) Attempting direct email match.. `n"
foreach ($slackUser in $users) {
    $user = New-Object User
    $user.id = $slackUser.id
    $user.FullName = $slackUser.name
    try {
        if ($null -ne $slackUser.profile.email) {
            $user.email = $slackUser.profile.email
            $emailSplit = $slackUser.profile.email.Split('@')
            $mailNickName = $emailSplit[0]
            $result = Get-AzureADUser -Filter "MailNickName eq '$($mailNickName)' or UserPrincipalName eq '$($slackUser.profile.email)' or proxyAddresses/any(c:c eq 'smtp:$($slackUser.profile.email)')"
            if ($null -ne $result) {
                $user.ExistsAzureAD = $true
                $user.UPN = $result.UserPrincipalName
                $assignedPlans = $result.assignedPlans
                foreach ($plan in $assignedPlans) {
                    if ($plan.ServicePlanId -eq "57ff2da0-773e-42df-b2af-ffb7a2317929") {
                        if ($plan.CapabilityStatus -eq "Enabled") {
                            $user.TeamsEnabled = $true
                        }
                        else {
                            $user.TeamsEnabled = $false
                        }
                    }
                }
                Write-Host -ForegroundColor Green "$(Get-Timestamp) Current User $($i) - AzureAD object found:" $result.MailNickName
                Write-Host -ForegroundColor Green "$(Get-Timestamp) Current User $($i) - Teams Enabled:" $user.TeamsEnabled
            }
            else {
                $user.ExistsAzureAD = $false
                Write-Host -ForegroundColor Yellow "$(Get-Timestamp) Current User $($i) - AzureAD object not found: " $slackUser.profile.email
            }
        }
        $i++
    }   
    catch
    {
        $user.ExistsAzureAD = $false
        Write-Host -ForegroundColor Yellow "$(Get-Timestamp) Current User $($i) - AzureAD object not found: $($i)" $user.profile.email
        $i++
    }
    $output.Add($user)
}

$output | Export-Csv -Path .\SlackToAzureADIdentityMapping.csv -NoTypeInformation
Write-Host "`n $(Get-Timestamp) Generated SlackToAzureADIdentityMapping.csv. Exiting..."
$output | Export-Csv -Path .\SlackToAzureADIdentityMapping.csv -NoTypeInformation
Write-Host "`n $(Get-Timestamp) Generated SlackToAzureADIdentityMapping.csv. Exiting..."
```

<span data-ttu-id="59ba4-163">Cuando haya terminado con esta sección, debería:</span><span class="sxs-lookup"><span data-stu-id="59ba4-163">When you’re done with this section, you should have:</span></span>
- <span data-ttu-id="59ba4-164">Tener una lista de canales por área de trabajo con estadísticas de uso.</span><span class="sxs-lookup"><span data-stu-id="59ba4-164">A list of Channels per Workspace with usage statistics.</span></span>
- <span data-ttu-id="59ba4-165">Tener una lista de aplicaciones de Slack con configuraciones por canal.</span><span class="sxs-lookup"><span data-stu-id="59ba4-165">A list of Slack Apps with configurations per channel.</span></span>
- <span data-ttu-id="59ba4-166">Haber determinado el tipo de historial de mensajes de Slack que quiere exportar (si hay alguno).</span><span class="sxs-lookup"><span data-stu-id="59ba4-166">Determined what type of Slack message history you want to export (if any).</span></span>
- <span data-ttu-id="59ba4-167">Tener una lista de los usuarios cuyas cuentas de Slack se asignan a cuentas profesionales o educativas de Microsoft y qué licencia de Teams tienen.</span><span class="sxs-lookup"><span data-stu-id="59ba4-167">A list of users whose Slack accounts map to Microsoft work or school accounts and which Teams license they have.</span></span>

## <a name="plan-your-teams-deployment"></a><span data-ttu-id="59ba4-168">Planeación de la implementación de Teams</span><span class="sxs-lookup"><span data-stu-id="59ba4-168">Plan your Teams deployment</span></span>
<span data-ttu-id="59ba4-169">Ha exportado lo que necesita de Slack (y dejado atrás lo que no necesita).</span><span class="sxs-lookup"><span data-stu-id="59ba4-169">You’ve exported what you need from Slack (and left behind anything you don’t need).</span></span> <span data-ttu-id="59ba4-170">Ahora es el momento de planear la forma en que implementará Teams e importará los datos de Slack.</span><span class="sxs-lookup"><span data-stu-id="59ba4-170">Now it’s time to plan how you’ll roll out Teams and import your Slack data.</span></span> <span data-ttu-id="59ba4-171">Esta es una gran oportunidad para evaluar qué ha funcionado bien para el equipo en función de su uso e incluir esos elementos en el plan de implementación de Teams.</span><span class="sxs-lookup"><span data-stu-id="59ba4-171">This is a great opportunity to assess what's worked well for the team based on usage and include those elements in your Teams deployment plan.</span></span> <span data-ttu-id="59ba4-172">Al final de esta sección, tendrá un plano técnico para sus usuarios, canales y aplicaciones de Teams.</span><span class="sxs-lookup"><span data-stu-id="59ba4-172">At the end of this section, you’ll have a blueprint for your Teams users, channels, and apps.</span></span> 

<span data-ttu-id="59ba4-173">El siguiente diagrama muestra un esquema general de las cosas que debe tratar en la implementación de Teams.</span><span class="sxs-lookup"><span data-stu-id="59ba4-173">The diagram below gives you a high-level outline of the things you’ll address in your Teams deployment.</span></span>

:::image type="content" source="media/migrate-slack-to-teams-image3.png" alt-text="Esquema general de la planeación para la implementación de Teams desde Slack.":::

### <a name="team-and-channel-structure"></a><span data-ttu-id="59ba4-175">Estructura de equipos y canales</span><span class="sxs-lookup"><span data-stu-id="59ba4-175">Team and channel structure</span></span>

<span data-ttu-id="59ba4-176">Un área de trabajo de Slack puede representar un único equipo, varios equipos o una organización completa.</span><span class="sxs-lookup"><span data-stu-id="59ba4-176">A Slack Workspace may represent a single team, multiple teams or an entire organization.</span></span> <span data-ttu-id="59ba4-177">Es importante comprender el alcance de las áreas de trabajo a medida que determina la estructura.</span><span class="sxs-lookup"><span data-stu-id="59ba4-177">It’s important to understand the scope of the Workspaces as you determine the structure.</span></span> <span data-ttu-id="59ba4-178">Lo más cercano a un equipo de Teams en Slack es el área de trabajo, que contiene un conjunto de canales.</span><span class="sxs-lookup"><span data-stu-id="59ba4-178">The closest relationship to a Teams team in Slack is the Workspace, which contains a collection of channels.</span></span> <span data-ttu-id="59ba4-179">En el diagrama siguiente se muestran 3 asignaciones de Slack a Teams diferentes, así como las directrices para elegir la adecuada para cada área de trabajo.</span><span class="sxs-lookup"><span data-stu-id="59ba4-179">The diagram below demonstrates 3 different Slack-to-Teams mappings, and guidance for picking the right one for each Workspace.</span></span>


|<span data-ttu-id="59ba4-180">Asignación de Slack a Teams </span><span class="sxs-lookup"><span data-stu-id="59ba4-180">Slack-to-Teams mapping</span></span> |  |
|---------|---------|
|<span data-ttu-id="59ba4-181">1 espacio de trabajo de Slack :arrow_right: 1 equipo</span><span class="sxs-lookup"><span data-stu-id="59ba4-181">1 Slack Workspace :arrow_right: 1 team</span></span>   | <span data-ttu-id="59ba4-182">Para áreas de trabajo de Slack más pequeñas, que necesitan menos de 200 canales.</span><span class="sxs-lookup"><span data-stu-id="59ba4-182">For smaller Slack workspaces that need fewer than 200 channels</span></span><br><span data-ttu-id="59ba4-183">Incluya un búfer para la planeación del crecimiento y los canales privados.</span><span class="sxs-lookup"><span data-stu-id="59ba4-183">Include a buffer for growth and private channel planning</span></span>  |
|<span data-ttu-id="59ba4-184">1 espacio de trabajo de Slack :arrow_right: varios equipos</span><span class="sxs-lookup"><span data-stu-id="59ba4-184">1 Slack Workspace :arrow_right: multiple teams</span></span>     | <span data-ttu-id="59ba4-185">Use los datos de análisis de su espacio de trabajo de Slack para crear grupos de canales lógicos, que se convertirán en la base de sus equipos.</span><span class="sxs-lookup"><span data-stu-id="59ba4-185">Use your Slack Workspace analytics data to create logical channel groupings, which become the basis of your teams</span></span>        |
|<span data-ttu-id="59ba4-186">2 espacios de trabajo de Slack :arrow_right: varios equipos</span><span class="sxs-lookup"><span data-stu-id="59ba4-186">2+ Slack Workspaces :arrow_right: multiple teams</span></span>     | <span data-ttu-id="59ba4-187">Use los datos de análisis de su espacio de trabajo de Slack para crear grupos de canales y equipos lógicos, que se convertirán en la base de sus equipos.</span><span class="sxs-lookup"><span data-stu-id="59ba4-187">Use your Slack Workspace analytics data to create logical team and channel groupings, which become the basis of your teams</span></span>        |

<span data-ttu-id="59ba4-188">Las soluciones de terceros tienen estadísticas de uso que le ayudarán a evaluar el nivel de actividad de un canal y el número de publicaciones que tiene.</span><span class="sxs-lookup"><span data-stu-id="59ba4-188">Third-party solutions have usage statistics to help you assess how active the channel is and how many posts there are.</span></span> <span data-ttu-id="59ba4-189">Normalmente, los canales que se usan a menudo serían candidatos para incluir en el planeamiento de equipos.</span><span class="sxs-lookup"><span data-stu-id="59ba4-189">Typically, channels that are frequently used would be candidates to include in your team planning.</span></span>

> [!TIP]
> <span data-ttu-id="59ba4-190">Conserve solo lo que sea necesario en su método para determinar qué canales se deben recrear en Teams.</span><span class="sxs-lookup"><span data-stu-id="59ba4-190">Retain only what is required in your approach to determine which channels to recreate in Teams.</span></span> <span data-ttu-id="59ba4-191">Para obtener más información, consulte [Información general sobre equipos y canales](teams-channels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="59ba4-191">To learn more, read [Overview of teams and channels](teams-channels-overview.md).</span></span> 

#### <a name="team-planning"></a><span data-ttu-id="59ba4-192">Planificación de equipos</span><span class="sxs-lookup"><span data-stu-id="59ba4-192">Team Planning</span></span>
<span data-ttu-id="59ba4-193">Con el inventario de canales que obtuvo en la sección de planificación anterior, trabaje con los propietarios y administradores de Slack para averiguar qué canales se deben convertir en equipos y cuáles deberían ser canales dentro de un equipo.</span><span class="sxs-lookup"><span data-stu-id="59ba4-193">Using the Channel inventory you compiled in the Planning section above, work with your Slack owners and admins to figure out which channels should become teams and which ones should become channels in a team.</span></span> <span data-ttu-id="59ba4-194">Use Excel o PowerBI para ayudar con este análisis: ambos pueden proporcionar información adicional para ayurdar a decidir qué canales se deben conservar.</span><span class="sxs-lookup"><span data-stu-id="59ba4-194">Use either Excel or PowerBI to help with this analysis - both can provide additional insights to help drive these discussions on which channels to retain.</span></span>

> [!TIP]
> <span data-ttu-id="59ba4-195">Actualmente, Teams tiene un límite de 200 canales por equipo.</span><span class="sxs-lookup"><span data-stu-id="59ba4-195">Teams currently has a 200-channel limit per team.</span></span> <span data-ttu-id="59ba4-196">Si la lista de canales se aproxima a ese límite, debe buscar una forma para dividirlos en dos equipos separados.</span><span class="sxs-lookup"><span data-stu-id="59ba4-196">If your list of channels is getting close to that limit, you should figure out a way to split them into two separate teams.</span></span>

### <a name="channel-history"></a><span data-ttu-id="59ba4-197">Historial de canales</span><span class="sxs-lookup"><span data-stu-id="59ba4-197">Channel History</span></span>

<span data-ttu-id="59ba4-198">Hay tanto soluciones gratuitas en GitHub como soluciones de pago que puede usar, en función de los requisitos de su organización, para conservar el historial de canales privados y públicos.</span><span class="sxs-lookup"><span data-stu-id="59ba4-198">There are both free solutions on GitHub and paid solutions you can use, depending on your organization’s requirements to retain Channel History of Public and Private channels.</span></span> <span data-ttu-id="59ba4-199">Además, esto se podría incluir en Teams con un script.</span><span class="sxs-lookup"><span data-stu-id="59ba4-199">Additionally, this could be scripted into Teams.</span></span>

<span data-ttu-id="59ba4-200">Una vez haya configurado la nueva estructura de equipos y canales en Teams, puede copiar los archivos exportados a las bibliotecas de documentos adecuadas en sus canales de Teams.</span><span class="sxs-lookup"><span data-stu-id="59ba4-200">Once you’ve set up your new team and channel structure in Teams, you can copy the exported files into the appropriate document libraries in your Teams channels.</span></span>

<span data-ttu-id="59ba4-201">Hay varios métodos que puede utilizar para automatizar la importación de contenido.</span><span class="sxs-lookup"><span data-stu-id="59ba4-201">To automate the importing of your content, there are several approaches you can consider.</span></span> <span data-ttu-id="59ba4-202">Existen soluciones gratuitas en GitHub ([ChannelSurf](https://github.com/tamhinsf/ChannelSurf) o el [Visor de exportación de Slack](https://github.com/hfaran/slack-export-viewer)) y soluciones de asociados.</span><span class="sxs-lookup"><span data-stu-id="59ba4-202">There are  free solutions on GitHub ([ChannelSurf](https://github.com/tamhinsf/ChannelSurf) or [Slack Export Viewer](https://github.com/hfaran/slack-export-viewer)) and partner solutions.</span></span> <span data-ttu-id="59ba4-203">Elija una solución en función de las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="59ba4-203">Choose a solution based on your organization’s needs.</span></span> 

### <a name="channel-files"></a><span data-ttu-id="59ba4-204">Archivos de canales</span><span class="sxs-lookup"><span data-stu-id="59ba4-204">Channel Files</span></span>

<span data-ttu-id="59ba4-205">La mayoría de las soluciones exportarán los archivos.</span><span class="sxs-lookup"><span data-stu-id="59ba4-205">Most solutions will export files.</span></span> <span data-ttu-id="59ba4-206">Sin embargo, normalmente se proporcionan como vínculos en el historial de canales que requieren una clave de API para recuperarlos mediante programación.</span><span class="sxs-lookup"><span data-stu-id="59ba4-206">However, they’re typically provided as links in the Channel History that require an API key to programmatically retrieve.</span></span>

<span data-ttu-id="59ba4-207">En el caso de los archivos almacenados en Slack, una vez que haya configurado los equipos y canales en Teams, podrá copiarlos mediante programación desde Slack al canal de destino de Teams.</span><span class="sxs-lookup"><span data-stu-id="59ba4-207">For files stored in Slack, once you’ve set up your teams and channels in Teams, you can programmatically copy them from Slack into the target Teams channel.</span></span>

<span data-ttu-id="59ba4-208">El siguiente script recupera archivos de Slack.</span><span class="sxs-lookup"><span data-stu-id="59ba4-208">The following script retrieves files from Slack.</span></span> <span data-ttu-id="59ba4-209">Realiza una búsqueda de la exportación especificada en su ordenador, crea una carpeta en cada canal de destino y descarga todos los archivos en esa ubicación.</span><span class="sxs-lookup"><span data-stu-id="59ba4-209">It searches the specified Slack export on your computer, creates a folder in each target channel, and downloads all of the files to that location.</span></span> <span data-ttu-id="59ba4-210">Hay soluciones de terceros que pueden extraer datos.</span><span class="sxs-lookup"><span data-stu-id="59ba4-210">Third-party solutions exist that can extract data.</span></span> <span data-ttu-id="59ba4-211">Si necesita ayuda con PowerShell, consulte [Introducción a Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span><span class="sxs-lookup"><span data-stu-id="59ba4-211">If you need help with PowerShell, read [Get started with Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span></span>



```azurepowershell
$ExportPath = ".\slackHistory"
$ExportContents = Get-ChildItem -path $ExportPath -Recurse
Function Get-TimeStamp {
    return "[{0:MM/dd/yy} {0:HH:mm:ss}]" -f (Get-Date)
}

class File {
    [string] $Name
    [string] $Title
    [string] $Channel
    [string] $DownloadURL
    [string] $MimeType
    [double] $Size
    [string] $ParentPath
    [string] $Time
}

$channelList = Get-Content -Raw -Path .\slackHistory\channels.json | ConvertFrom-Json
$Files = New-Object -TypeName System.Collections.ObjectModel.Collection["File"]

Write-Host -ForegroundColor Green "$(Get-TimeStamp) Starting Step 1 (processing channel export for files) of 2. Total Channel Count: $($channelList.Count)"
#Iterate through each Channel listed in the Archive
foreach ($channel in $channelList) {
    #Iterate through Channel folders from the Export
    foreach ($folder in $ExportContents)
    {
        #If Channel Name matches..
        if ($channel.name -eq $folder){
            $channelJsons = Get-ChildItem -Path $folder.FullName -File
            Write-Host -ForegroundColor White "$(Get-TimeStamp) Info: Starting to process $($channelJsons.Count) days of content for #$($channel.name)."
            #Start processing the daily JSON for files
            foreach ($json in $channelJsons){
                $currentJson = Get-Content -Raw -Path $json.FullName | ConvertFrom-Json
                #Write-Host -ForegroundColor Yellow "$(Get-TimeStamp) Info: Processing $($json.Name) in #$($channel.name).."
                #Iterate through every action
                foreach ($entry in $currentJson){
                    #If the action contained file(s)..
                    if($null -ne $entry.files){
                        #Iterate through each file and add it to the List of Files to download
                        foreach ($item in $entry.Files) {
                        $file = New-Object -TypeName File
                            if ($null -ne $item.url_private_download){
                                $file.Name = $item.name
                                $file.Title = $item.Title
                                $file.Channel = $channel.name
                                $file.DownloadURL = $item.url_private_download
                                $file.MimeType = $item.mimetype
                                $file.Size = $item.size
                                $file.ParentPath = $folder.FullName
                                $file.Time = $item.created
                                $files.Add($file)
                            }
                        }
                    }
                }
            }
        }
    }
}
Write-Host -ForegroundColor Green "$(Get-TimeStamp) Step 1 of 2 complete. `n"

Write-Host -ForegroundColor Green "$(Get-TimeStamp) Starting step 2 (creating folders and downloading files) of 2."
#Determine which Files folders need to be created
$FoldersToMake = New-Object System.Collections.ObjectModel.Collection["string"]
foreach ($file in $files){
    if ($FoldersToMake -notcontains $file.Channel){
        $FoldersToMake.Add($file.Channel)
    }
}

#Create Folders
foreach ($folder in $FoldersToMake){
    #$fullFolderPath = $file.ParentPath + "\Files"
    $fullFolderPath = $ExportPath +"\$($folder)"
    $fullFilesPath = $ExportPath +"\$($folder)\Files"
    if (-not (Test-Path $fullFilesPath)){
        New-Item -Path $fullFolderPath  -Name "Files" -ItemType "directory"
    }
}

#Downloading Files
foreach ($file in $files)
{
    Write-Host -ForegroundColor Yellow "$(Get-TimeStamp) Downloading $($file.Name)."
    $fullFilePath = $file.ParentPath + "\Files\" + $file.Name
        if (-not (Test-Path $fullFilePath)){
            try{
                $request = (New-Object System.Net.WebClient).DownloadFile($file.DownloadURL, $fullFilePath)
            }
            catch [System.Net.WebException]{
                Write-Host -ForegroundColor Red "$(Get-TimeStamp) Error: Unable to download $($file.Name) to $($fullFilePath)"
            }   
        }
        else {
            try{
                $extensionPosition = $file.name.LastIndexOf('.')
                $splitFileName = $file.name.Substring(0,$extensionPosition)
                $splitFileExtention = $file.name.Substring($extensionPosition)
                $newFileName = $splitFileName + $file.Time + $splitFileExtention
                $fullFilePath = $file.ParentPath + "\Files\" + $newFileName
                $request = (New-Object System.Net.WebClient).DownloadFile($file.DownloadURL, $fullFilePath)
            }
            catch [System.Net.WebException]{
                Write-Host -ForegroundColor Red "$(Get-TimeStamp) Error: Unable to download $($file.Name) to $($fullFilePath)"
            }   
        }
}
Write-Host -ForegroundColor Green "$(Get-TimeStamp) Step 2 of 2 complete. `n"
Write-Host -ForegroundColor Green "$(Get-TimeStamp) Exiting.."
```


### <a name="apps-and-custom-integrations"></a><span data-ttu-id="59ba4-212">Aplicaciones e integraciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="59ba4-212">Apps and Custom Integrations</span></span>
<span data-ttu-id="59ba4-213">Revise su lista de aplicaciones e integraciones personalizadas de Slack (con sus configuraciones) y elija las que quiere migrar a Teams.</span><span class="sxs-lookup"><span data-stu-id="59ba4-213">Review your list of Slack apps and custom integrations (with configurations) and decide which ones you want to move to Teams.</span></span> <span data-ttu-id="59ba4-214">Compruebe el catálogo de soluciones de Teams para ver si hay una aplicación disponible.</span><span class="sxs-lookup"><span data-stu-id="59ba4-214">Check the Teams Marketplace to see if an app is available.</span></span> <span data-ttu-id="59ba4-215">Si no es así, es probable que haya alternativas.</span><span class="sxs-lookup"><span data-stu-id="59ba4-215">If not, there are likely alternatives.</span></span> 

<span data-ttu-id="59ba4-216">Para averiguar qué aplicaciones agregar a Teams, es importante que comprenda cómo se usa la aplicación.</span><span class="sxs-lookup"><span data-stu-id="59ba4-216">To figure out which apps to add to Teams, it’s important to understand how the app is being used.</span></span> <span data-ttu-id="59ba4-217">Al realizar la pregunta "¿qué funcionalidad ofrece la aplicación para este canal?", obtendrá información sobre los resultados que proporciona la aplicación.</span><span class="sxs-lookup"><span data-stu-id="59ba4-217">By asking the question "what functionality is the app providing to this channel?", you'll learn about the outcome the app is delivering.</span></span> 

<span data-ttu-id="59ba4-218">En muchos casos, las aplicaciones reciben principalmente datos basados en eventos desde un servicio externo (por ejemplo, el sistema de supervisión) e insertan un mensaje en Slack.</span><span class="sxs-lookup"><span data-stu-id="59ba4-218">In many cases, apps primarily receive event-driven data from an external service (for example, monitoring system) and push a message into Slack.</span></span> <span data-ttu-id="59ba4-219">Puede obtener el mismo resultado si usa un conector de Microsoft 365 que pueda insertar mensajes en Teams basándose en eventos.</span><span class="sxs-lookup"><span data-stu-id="59ba4-219">You can achieve the same outcome by using a Microsoft 365 Connector that can push messages into Teams based on events.</span></span>

<span data-ttu-id="59ba4-220">A continuación se muestran ejemplos de soluciones de Slack en las que se utilizó un conector de Microsoft 365 en Teams para la integración.</span><span class="sxs-lookup"><span data-stu-id="59ba4-220">Below are examples of Slack solutions where a Microsoft 365 Connector was used in Teams for integration.</span></span>
- <span data-ttu-id="59ba4-221">Ansible</span><span class="sxs-lookup"><span data-stu-id="59ba4-221">Ansible</span></span>
  - <span data-ttu-id="59ba4-222">Las alertas se pueden enviar a Teams mediante [webhook de Ansible](https://docs.ansible.com/ansible-tower/latest/html/userguide/notifications.html#webhook).</span><span class="sxs-lookup"><span data-stu-id="59ba4-222">Alerts can be sent to Teams via [Ansible webhook](https://docs.ansible.com/ansible-tower/latest/html/userguide/notifications.html#webhook)</span></span>
- <span data-ttu-id="59ba4-223">New Relic</span><span class="sxs-lookup"><span data-stu-id="59ba4-223">New Relic</span></span>
  - <span data-ttu-id="59ba4-224">Pruebe esta solución de usuario para el [envío de alertas New Relic a Teams](https://discuss.newrelic.com/t/new-relic-alerts-not-working-with-microsoft-teams/48609/3).</span><span class="sxs-lookup"><span data-stu-id="59ba4-224">Check out this user solution for [sending New Relic alerts to Teams](https://discuss.newrelic.com/t/new-relic-alerts-not-working-with-microsoft-teams/48609/3)</span></span>
- <span data-ttu-id="59ba4-225">Nagios</span><span class="sxs-lookup"><span data-stu-id="59ba4-225">Nagios</span></span>
  - <span data-ttu-id="59ba4-226">Las alertas pueden integrarse en la actualidad mediante conectores.</span><span class="sxs-lookup"><span data-stu-id="59ba4-226">Alerts can be integrated today via Connectors.</span></span> <span data-ttu-id="59ba4-227">https://github.com/isaac-galvan/nagios-teams-notify</span><span class="sxs-lookup"><span data-stu-id="59ba4-227">https://github.com/isaac-galvan/nagios-teams-notify</span></span>
- <span data-ttu-id="59ba4-228">ZenDesk</span><span class="sxs-lookup"><span data-stu-id="59ba4-228">ZenDesk</span></span>
  - <span data-ttu-id="59ba4-229">La aplicación se encuentra en la tienda de Teams.</span><span class="sxs-lookup"><span data-stu-id="59ba4-229">App exists in Teams Store</span></span>
- <span data-ttu-id="59ba4-230">Jenkins</span><span class="sxs-lookup"><span data-stu-id="59ba4-230">Jenkins</span></span>
  - <span data-ttu-id="59ba4-231">Las alertas se pueden enviar a Teams con [conector de Office 365 de Jenkins](https://plugins.jenkins.io/Office-365-Connector).</span><span class="sxs-lookup"><span data-stu-id="59ba4-231">Alerts can be sent to Teams using [Jenkins’s Office 365 Connector](https://plugins.jenkins.io/Office-365-Connector)</span></span>


### <a name="user-readiness-and-adoption-plan"></a><span data-ttu-id="59ba4-232">Preparación del usuario y plan de adopción</span><span class="sxs-lookup"><span data-stu-id="59ba4-232">User readiness and adoption plan</span></span>
<span data-ttu-id="59ba4-233">El pilar de cualquier implementación correcta de software depende de cómo estén preparados los usuarios para el cambio.</span><span class="sxs-lookup"><span data-stu-id="59ba4-233">The cornerstone of any successful software deployment hinges on how prepared users are for the change.</span></span> <span data-ttu-id="59ba4-234">Los usuarios de su organización que usan Slack comprenderán fácilmente los conceptos de Teams, pero sigue siendo necesario un aprendizaje para ayudarles a realizar una transición sin problemas.</span><span class="sxs-lookup"><span data-stu-id="59ba4-234">Users in your organization using Slack will easily understand Teams concepts, but training is still needed to help them make a smooth transition.</span></span> <span data-ttu-id="59ba4-235">Para obtener un conjunto completo de recursos para la adopción de Teams, vaya al [centro de adopción de Teams](adopt-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="59ba4-235">For a comprehensive set of Teams adoption resources, go to the [Teams adoption hub](adopt-microsoft-teams-landing-page.md).</span></span>

<span data-ttu-id="59ba4-236">Por ejemplo, los dos productos cuentan con canales, pero estos se usan de forma diferente en cada producto.</span><span class="sxs-lookup"><span data-stu-id="59ba4-236">For example, both products feature channels, but they’re used differently in each product.</span></span> <span data-ttu-id="59ba4-237">Por ejemplo, a menudo un canal en Slack se usa como un chat en Teams, para conversaciones transaccionales y a corto plazo.</span><span class="sxs-lookup"><span data-stu-id="59ba4-237">For example, often a Channel in Slack is used like a chat in Teams for short-term, transactional conversations.</span></span> <span data-ttu-id="59ba4-238">Otras diferencias notables se encuentran en la configuración de las notificaciones y en las conversaciones encadenadas o no encadenadas.</span><span class="sxs-lookup"><span data-stu-id="59ba4-238">Other notable differences are around threaded/non-threaded conversations and tuning notification settings.</span></span>

<span data-ttu-id="59ba4-239">Consulte nuestra variada biblioteca de [Vídeos de aprendizaje de Teams para usuarios finales](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7).</span><span class="sxs-lookup"><span data-stu-id="59ba4-239">Check out our rich library of [End-user Teams video training](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7).</span></span> 

## <a name="move-to-teams"></a><span data-ttu-id="59ba4-240">Migración a Teams</span><span class="sxs-lookup"><span data-stu-id="59ba4-240">Move to Teams</span></span> 
<span data-ttu-id="59ba4-241">Ahora que ha definido el plan de transición, puede empezar a crear sus equipos y canales en Teams.</span><span class="sxs-lookup"><span data-stu-id="59ba4-241">Now that your transition plan is defined, you can begin creating your teams and channels in Teams.</span></span> 

<span data-ttu-id="59ba4-242">Una vez que haya creado los equipos y canales, inicie la copia de archivos de los canales de Slack a Teams y configure las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="59ba4-242">Once you’ve created your teams & channels, begin copying files from Slack channels into Teams and configuring your apps.</span></span> <span data-ttu-id="59ba4-243">Si utiliza una solución para conservar el historial, también puede configurarla ahora.</span><span class="sxs-lookup"><span data-stu-id="59ba4-243">If you’re using a solution to retain history, that can be configured now as well.</span></span> <span data-ttu-id="59ba4-244">Una vez hecho estará listo para iniciar la concesión de licencias para los usuarios (si aún no tienen licencia) y agregarlos a los equipos adecuados.</span><span class="sxs-lookup"><span data-stu-id="59ba4-244">Then you’re ready to start licensing users (if they aren’t licensed already) and adding them to the appropriate teams.</span></span> <span data-ttu-id="59ba4-245">Para reducir la necesidad de exportaciones y copias adicionales de archivos, considere la posibilidad de eliminar el acceso a Slack en una fecha acordada que coincida con la adición de cada usuario al equipo.</span><span class="sxs-lookup"><span data-stu-id="59ba4-245">To reduce the need for additional exports and file copies, consider removing Slack access at an agreed-upon date that coincides with each user’s addition to the team.</span></span> <span data-ttu-id="59ba4-246">Así evitará tener que volver a exportar e importar los cambios en los archivos y el historial.</span><span class="sxs-lookup"><span data-stu-id="59ba4-246">This avoids needing to re-export and import delta changes on files and history.</span></span>

<span data-ttu-id="59ba4-247">Siga los pasos del diagrama siguiente para implementar Teams en su organización.</span><span class="sxs-lookup"><span data-stu-id="59ba4-247">Follow the steps in the diagram below to roll out Teams in your organization.</span></span> <span data-ttu-id="59ba4-248">Para obtener más información, consulte [Cómo implementar equipos](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="59ba4-248">For more information, check out [How to roll out Teams](How-to-roll-out-teams.md).</span></span>


:::image type="content" source="media/migrate-slack-to-teams-image4.png" alt-text="Diagrama en el que se muestran los pasos para migrar a Teams desde Slack.":::
