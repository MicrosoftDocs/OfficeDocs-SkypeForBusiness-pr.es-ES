---
title: Configurar el panel de calidad de llamadas (CQD)
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Obtenga información sobre cómo activar y usar el Panel de calidad de llamadas y obtener informes de resumen de la calidad de las llamadas.
ms.openlocfilehash: c71cb25732a99f207467a988ad0db54c959d15f4
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52254307"
---
# <a name="set-up-call-quality-dashboard-cqd"></a><span data-ttu-id="d47af-103">Configurar el panel de calidad de llamadas (CQD)</span><span class="sxs-lookup"><span data-stu-id="d47af-103">Set up Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="d47af-104">Abra el Panel de calidad de llamadas de Microsoft (CQD) en [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (inicie sesión con sus credenciales de administrador).</span><span class="sxs-lookup"><span data-stu-id="d47af-104">Open the Microsoft Call Quality Dashboard (CQD) at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (sign in with your admin credentials).</span></span> <span data-ttu-id="d47af-105">O bien, vaya al centro Teams de administración y seleccione **Panel de calidad de llamadas.**</span><span class="sxs-lookup"><span data-stu-id="d47af-105">Or go to the Teams admin center and select **Call Quality Dashboard**.</span></span> 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Captura de pantalla del botón Panel de calidad de llamadas Teams centro de administración":::

<span data-ttu-id="d47af-107">En la página que se abre, haga clic en **Iniciar sesión** y escriba su cuenta de administrador global o Microsoft Teams cuenta de administrador.</span><span class="sxs-lookup"><span data-stu-id="d47af-107">On the page that opens, click **Sign in** and enter your Global Administrator account or Microsoft Teams Administrator account information.</span></span> <span data-ttu-id="d47af-108">Después de la primera vez que inicie sesión, CQD empezará a recopilar y procesar datos.</span><span class="sxs-lookup"><span data-stu-id="d47af-108">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="d47af-109">Tenga en cuenta que puede tardar una o más horas en procesar datos suficientes para mostrar resultados significativos en los informes.</span><span class="sxs-lookup"><span data-stu-id="d47af-109">Keep in mind that it may take one or more hours to process enough data to display meaningful results in the reports.</span></span>

<span data-ttu-id="d47af-110">CQD muestra la calidad de las llamadas y reuniones, a nivel de toda la organización, para Microsoft Teams, Skype Empresarial Online y Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d47af-110">CQD shows call and meeting quality, at an org-wide level, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="d47af-111">Para usar CQD con Skype Empresarial Server 2019, tendrá que configurar El conector de [datos de llamadas](/skypeforbusiness/hybrid/configure-call-data-connector).</span><span class="sxs-lookup"><span data-stu-id="d47af-111">To use CQD with Skype for Business Server 2019, you'll have to [Configure Call Data Connector](/skypeforbusiness/hybrid/configure-call-data-connector).</span></span> <span data-ttu-id="d47af-112">Consulte [Planear el conector de datos de llamadas](/skypeforbusiness/hybrid/plan-call-data-connector) antes de empezar.</span><span class="sxs-lookup"><span data-stu-id="d47af-112">See [Plan Call Data Connector](/skypeforbusiness/hybrid/plan-call-data-connector) before you start.</span></span>


## <a name="assign-admin-roles-for-access-to-cqd"></a><span data-ttu-id="d47af-113">Asignar roles de administrador para el acceso a CQD</span><span class="sxs-lookup"><span data-stu-id="d47af-113">Assign admin roles for access to CQD</span></span>

<span data-ttu-id="d47af-114">Asigne [roles](/microsoft-365/admin/add-users/about-admin-roles) para obtener acceso a CQD a las personas que necesitan usarlo.</span><span class="sxs-lookup"><span data-stu-id="d47af-114">Assign [roles](/microsoft-365/admin/add-users/about-admin-roles) for accessing CQD to the people who need to use it.</span></span>

<span data-ttu-id="d47af-115">Si desea que los usuarios que no son administradores (como ingenieros de soporte técnico y agentes de soporte técnico) usen el Panel de calidad de llamadas, puede asignar a esos usuarios uno de los siguientes roles, lo que da acceso a CQD.</span><span class="sxs-lookup"><span data-stu-id="d47af-115">If you want non-admin users (such as support engineers and helpdesk agents) to use Call Quality Dashboard, you can assign those users one of the following roles, which gives access to CQD.</span></span> 


|  |<span data-ttu-id="d47af-116">Ver informes</span><span class="sxs-lookup"><span data-stu-id="d47af-116">View reports</span></span>  |<span data-ttu-id="d47af-117">Ver campos EUII</span><span class="sxs-lookup"><span data-stu-id="d47af-117">View EUII fields</span></span>  |<span data-ttu-id="d47af-118">Crear informes</span><span class="sxs-lookup"><span data-stu-id="d47af-118">Create reports</span></span>  |<span data-ttu-id="d47af-119">Upload datos de creación</span><span class="sxs-lookup"><span data-stu-id="d47af-119">Upload building data</span></span>  |
|---------|:-------:|:-------:|:-------:|:-------:|
|<span data-ttu-id="d47af-120">Administrador global</span><span class="sxs-lookup"><span data-stu-id="d47af-120">Global Administrator</span></span>     |<span data-ttu-id="d47af-121">Sí</span><span class="sxs-lookup"><span data-stu-id="d47af-121">Yes</span></span>         |<span data-ttu-id="d47af-122">Sí</span><span class="sxs-lookup"><span data-stu-id="d47af-122">Yes</span></span>         |<span data-ttu-id="d47af-123">Sí</span><span class="sxs-lookup"><span data-stu-id="d47af-123">Yes</span></span>         |<span data-ttu-id="d47af-124">Sí</span><span class="sxs-lookup"><span data-stu-id="d47af-124">Yes</span></span>         |
|<span data-ttu-id="d47af-125">Teams Administrador</span><span class="sxs-lookup"><span data-stu-id="d47af-125">Teams Administrator</span></span>     |<span data-ttu-id="d47af-126">Sí</span><span class="sxs-lookup"><span data-stu-id="d47af-126">Yes</span></span>         |<span data-ttu-id="d47af-127">Sí</span><span class="sxs-lookup"><span data-stu-id="d47af-127">Yes</span></span>         |<span data-ttu-id="d47af-128">Sí</span><span class="sxs-lookup"><span data-stu-id="d47af-128">Yes</span></span>         |<span data-ttu-id="d47af-129">Sí</span><span class="sxs-lookup"><span data-stu-id="d47af-129">Yes</span></span>         |
|<span data-ttu-id="d47af-130">Administrador de comunicaciones de Teams</span><span class="sxs-lookup"><span data-stu-id="d47af-130">Teams Communications Administrator</span></span>     |<span data-ttu-id="d47af-131">Sí</span><span class="sxs-lookup"><span data-stu-id="d47af-131">Yes</span></span>         |<span data-ttu-id="d47af-132">Sí</span><span class="sxs-lookup"><span data-stu-id="d47af-132">Yes</span></span>         |<span data-ttu-id="d47af-133">Sí</span><span class="sxs-lookup"><span data-stu-id="d47af-133">Yes</span></span>         |<span data-ttu-id="d47af-134">Sí</span><span class="sxs-lookup"><span data-stu-id="d47af-134">Yes</span></span>         |
|<span data-ttu-id="d47af-135">Ingeniero de soporte en comunicaciones de Teams</span><span class="sxs-lookup"><span data-stu-id="d47af-135">Teams Communications Support Engineer</span></span>     |<span data-ttu-id="d47af-136">Sí</span><span class="sxs-lookup"><span data-stu-id="d47af-136">Yes</span></span>         |<span data-ttu-id="d47af-137">Sí</span><span class="sxs-lookup"><span data-stu-id="d47af-137">Yes</span></span>         |<span data-ttu-id="d47af-138">Sí</span><span class="sxs-lookup"><span data-stu-id="d47af-138">Yes</span></span>         |<span data-ttu-id="d47af-139">No</span><span class="sxs-lookup"><span data-stu-id="d47af-139">No</span></span>         |
|<span data-ttu-id="d47af-140">Teams Especialista en soporte técnico de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="d47af-140">Teams Communications Support Specialist</span></span>     |<span data-ttu-id="d47af-141">Sí</span><span class="sxs-lookup"><span data-stu-id="d47af-141">Yes</span></span>         |<span data-ttu-id="d47af-142">No</span><span class="sxs-lookup"><span data-stu-id="d47af-142">No</span></span>         |<span data-ttu-id="d47af-143">Sí</span><span class="sxs-lookup"><span data-stu-id="d47af-143">Yes</span></span>         |<span data-ttu-id="d47af-144">No</span><span class="sxs-lookup"><span data-stu-id="d47af-144">No</span></span>         |
|<span data-ttu-id="d47af-145">Skype Empresarial Administrador</span><span class="sxs-lookup"><span data-stu-id="d47af-145">Skype for Business Administrator</span></span>     |<span data-ttu-id="d47af-146">Sí</span><span class="sxs-lookup"><span data-stu-id="d47af-146">Yes</span></span>         |<span data-ttu-id="d47af-147">Sí</span><span class="sxs-lookup"><span data-stu-id="d47af-147">Yes</span></span>         |<span data-ttu-id="d47af-148">Sí</span><span class="sxs-lookup"><span data-stu-id="d47af-148">Yes</span></span>         |<span data-ttu-id="d47af-149">Sí</span><span class="sxs-lookup"><span data-stu-id="d47af-149">Yes</span></span>         |
|<span data-ttu-id="d47af-150">Lector global</span><span class="sxs-lookup"><span data-stu-id="d47af-150">Global Reader</span></span> |<span data-ttu-id="d47af-151">Sí</span><span class="sxs-lookup"><span data-stu-id="d47af-151">Yes</span></span>         |<span data-ttu-id="d47af-152">Sí</span><span class="sxs-lookup"><span data-stu-id="d47af-152">Yes</span></span>         |<span data-ttu-id="d47af-153">Sí</span><span class="sxs-lookup"><span data-stu-id="d47af-153">Yes</span></span>         |<span data-ttu-id="d47af-154">No</span><span class="sxs-lookup"><span data-stu-id="d47af-154">No</span></span>         |
|<span data-ttu-id="d47af-155">Lector de<sup>informes 1</sup></span><span class="sxs-lookup"><span data-stu-id="d47af-155">Reports Reader<sup>1</sup></span></span>     |<span data-ttu-id="d47af-156">Sí</span><span class="sxs-lookup"><span data-stu-id="d47af-156">Yes</span></span>         |<span data-ttu-id="d47af-157">No</span><span class="sxs-lookup"><span data-stu-id="d47af-157">No</span></span>         |<span data-ttu-id="d47af-158">Sí</span><span class="sxs-lookup"><span data-stu-id="d47af-158">Yes</span></span>         |<span data-ttu-id="d47af-159">No</span><span class="sxs-lookup"><span data-stu-id="d47af-159">No</span></span>         |

<span data-ttu-id="d47af-160"><sup>1</sup> Además de leer informes de CQD, [](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) el Lector de informes puede ver todos los informes de actividad en el centro de administración y cualquier informe del paquete de contenido de [Microsoft 365 adopción.](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)</span><span class="sxs-lookup"><span data-stu-id="d47af-160"><sup>1</sup> In addition to reading CQD reports, the Reports Reader can view all the [activity reports](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) in the admin center and any reports from the [Microsoft 365 Adoption content pack](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).</span></span>

> [!NOTE]
> <span data-ttu-id="d47af-161">Si no ve [EUII (información](CQD-data-and-reports.md#euii-data) de identificación del usuario final) y tiene uno de los roles permitidos para ver esta información, tenga en cuenta que CQD solo conserva EUII durante 28 días.</span><span class="sxs-lookup"><span data-stu-id="d47af-161">If you're not seeing [EUII (end-user identifiable information)](CQD-data-and-reports.md#euii-data) and you have one of the roles that's permitted to see this information, keep in mind that CQD only keeps EUII for 28 days.</span></span> <span data-ttu-id="d47af-162">Se elimina cualquier cosa anterior a 28 días.</span><span class="sxs-lookup"><span data-stu-id="d47af-162">Anything older than 28 days is deleted.</span></span>

<span data-ttu-id="d47af-163">Para obtener más información sobre estos roles, vea Acerca [de Office 365 de administrador](/office365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="d47af-163">For more information about these roles, see [About Office 365 admin roles](/office365/admin/add-users/about-admin-roles).</span></span>


<span data-ttu-id="d47af-164">Después de la primera vez que inicie sesión, CQD empezará a recopilar y procesar datos.</span><span class="sxs-lookup"><span data-stu-id="d47af-164">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="d47af-165">A partir de diciembre de 2019, todavía puede acceder a la versión anterior de CQD (cqd.lync.com), aunque el portal heredado le proporciona un vínculo al CQD más reciente (cqd.teams.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="d47af-165">As of December 2019, you can still access the older version of CQD (cqd.lync.com), although the legacy portal gives you a link to the latest CQD (cqd.teams.microsoft.com).</span></span> <span data-ttu-id="d47af-166">Finalmente, la versión anterior de CQD se retirará.</span><span class="sxs-lookup"><span data-stu-id="d47af-166">Eventually, the older version of CQD will be decommissioned.</span></span> <span data-ttu-id="d47af-167">A partir del 1 de julio de 2020, la versión anterior de CQD tiene acceso a los datos del CQD más reciente.</span><span class="sxs-lookup"><span data-stu-id="d47af-167">As of July 1, 2020, the older version of CQD accesses data from the latest CQD.</span></span>


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a><span data-ttu-id="d47af-168">Migrar datos de creación e informes desde la versión anterior de CQD</span><span class="sxs-lookup"><span data-stu-id="d47af-168">Migrate building data and reports from previous version of CQD</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d47af-169">A partir del 1 de julio de 2020, ya no puede migrar datos de creación e informes desde el CQD antiguo ( https://CQD.lync.com) .</span><span class="sxs-lookup"><span data-stu-id="d47af-169">As of July 1, 2020, you can no longer migrate building data and reports from the old CQD (https://CQD.lync.com).</span></span> 



## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="d47af-170">Usar Power BI para analizar datos CQD</span><span class="sxs-lookup"><span data-stu-id="d47af-170">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="d47af-171">Nuevo en enero de 2020: [Descargar Power BI plantillas de consulta de CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="d47af-171">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="d47af-172">Plantillas Power BI personalizables que puede usar para analizar e informar de los datos de CQD.</span><span class="sxs-lookup"><span data-stu-id="d47af-172">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="d47af-173">Lea [Usar Power BI para analizar datos CQD](CQD-Power-BI-query-templates.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d47af-173">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>


## <a name="related-topics"></a><span data-ttu-id="d47af-174">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d47af-174">Related topics</span></span>

[<span data-ttu-id="d47af-175">Mejorar y supervisar la calidad de las llamadas Teams</span><span class="sxs-lookup"><span data-stu-id="d47af-175">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="d47af-176">¿Qué es CQD?</span><span class="sxs-lookup"><span data-stu-id="d47af-176">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="d47af-177">Upload inquilino y datos de creación</span><span class="sxs-lookup"><span data-stu-id="d47af-177">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="d47af-178">Datos e informes de CQD</span><span class="sxs-lookup"><span data-stu-id="d47af-178">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="d47af-179">Usar CQD para administrar la calidad de las llamadas y las reuniones</span><span class="sxs-lookup"><span data-stu-id="d47af-179">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="d47af-180">Dimensiones y medidas disponibles en CQD</span><span class="sxs-lookup"><span data-stu-id="d47af-180">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="d47af-181">Clasificación de secuencias en CQD</span><span class="sxs-lookup"><span data-stu-id="d47af-181">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="d47af-182">Usar Power BI para analizar datos CQD</span><span class="sxs-lookup"><span data-stu-id="d47af-182">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)