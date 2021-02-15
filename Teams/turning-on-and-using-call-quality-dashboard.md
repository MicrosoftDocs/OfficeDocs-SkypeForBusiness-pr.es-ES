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
description: Obtenga información sobre cómo activar y usar el panel de calidad de llamadas y obtener informes de resumen de la calidad de las llamadas.
ms.openlocfilehash: 60363ed86e4e073b7ca5a752261ac806188900b1
ms.sourcegitcommit: ac73536f790f83a61eeb2eb8c6b71662f7bd26fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "50112843"
---
# <a name="set-up-call-quality-dashboard-cqd"></a><span data-ttu-id="085d6-103">Configurar el panel de calidad de llamadas (CQD)</span><span class="sxs-lookup"><span data-stu-id="085d6-103">Set up Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="085d6-104">Abra el panel de calidad de llamadas (CQD) de Microsoft [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) en (inicie sesión con sus credenciales de administrador).</span><span class="sxs-lookup"><span data-stu-id="085d6-104">Open the Microsoft Call Quality Dashboard (CQD) at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (sign in with your admin credentials).</span></span> <span data-ttu-id="085d6-105">O bien, vaya al Centro de administración de Teams y seleccione **Panel de calidad de llamadas.**</span><span class="sxs-lookup"><span data-stu-id="085d6-105">Or go to the Teams admin center and select **Call Quality Dashboard**.</span></span> 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Captura de pantalla del botón Panel de calidad de llamadas en el Centro de administración de Teams":::

<span data-ttu-id="085d6-107">En la página que se abre, haga clic en **Iniciar sesión** y escriba la información de su cuenta de administrador global o de administrador de servicios de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="085d6-107">On the page that opens, click **Sign in** and enter your Global Administrator account or Microsoft Teams Service Administrator account information.</span></span> <span data-ttu-id="085d6-108">Después de iniciar sesión por primera vez, el CQD comenzará a recopilar y procesar datos.</span><span class="sxs-lookup"><span data-stu-id="085d6-108">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="085d6-109">Tenga en cuenta que puede tardar una o más horas en procesar los datos suficientes para mostrar resultados significativos en los informes.</span><span class="sxs-lookup"><span data-stu-id="085d6-109">Keep in mind that it may take one or more hours to process enough data to display meaningful results in the reports.</span></span>

<span data-ttu-id="085d6-110">El CQD muestra la calidad de las llamadas y reuniones, a nivel de toda la organización, para Microsoft Teams, Skype Empresarial Online y Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="085d6-110">CQD shows call and meeting quality, at an org-wide level, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="085d6-111">Para usar el CQD con Skype Empresarial Server 2019, tendrá que configurar el conector de [datos de llamadas.](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector)</span><span class="sxs-lookup"><span data-stu-id="085d6-111">To use CQD with Skype for Business Server 2019, you'll have to [Configure Call Data Connector](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector).</span></span> <span data-ttu-id="085d6-112">Vea [Planear conector de datos de llamadas](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) antes de empezar.</span><span class="sxs-lookup"><span data-stu-id="085d6-112">See [Plan Call Data Connector](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) before you start.</span></span>


## <a name="assign-admin-roles-for-access-to-cqd"></a><span data-ttu-id="085d6-113">Asignar roles de administrador para obtener acceso al CQD</span><span class="sxs-lookup"><span data-stu-id="085d6-113">Assign admin roles for access to CQD</span></span>

<span data-ttu-id="085d6-114">Asigne [roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) para acceder al CQD a las personas que necesitan usarlo.</span><span class="sxs-lookup"><span data-stu-id="085d6-114">Assign [roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) for accessing CQD to the people who need to use it.</span></span>

<span data-ttu-id="085d6-115">Si desea que los usuarios que no son administradores (como ingenieros de soporte técnico y agentes del departamento de soporte técnico) usen el panel de calidad de llamadas, puede asignar a esos usuarios uno de los siguientes roles, que le da acceso al panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="085d6-115">If you want non-admin users (such as support engineers and helpdesk agents) to use Call Quality Dashboard, you can assign those users one of the following roles, which gives access to CQD.</span></span> 


|  |<span data-ttu-id="085d6-116">Ver informes</span><span class="sxs-lookup"><span data-stu-id="085d6-116">View reports</span></span>  |<span data-ttu-id="085d6-117">Ver campos EUII</span><span class="sxs-lookup"><span data-stu-id="085d6-117">View EUII fields</span></span>  |<span data-ttu-id="085d6-118">Crear informes</span><span class="sxs-lookup"><span data-stu-id="085d6-118">Create reports</span></span>  |<span data-ttu-id="085d6-119">Cargar datos de creación</span><span class="sxs-lookup"><span data-stu-id="085d6-119">Upload building data</span></span>  |
|---------|:-------:|:-------:|:-------:|:-------:|
|<span data-ttu-id="085d6-120">Administrador global</span><span class="sxs-lookup"><span data-stu-id="085d6-120">Global Administrator</span></span>     |<span data-ttu-id="085d6-121">Sí</span><span class="sxs-lookup"><span data-stu-id="085d6-121">Yes</span></span>         |<span data-ttu-id="085d6-122">Sí</span><span class="sxs-lookup"><span data-stu-id="085d6-122">Yes</span></span>         |<span data-ttu-id="085d6-123">Sí</span><span class="sxs-lookup"><span data-stu-id="085d6-123">Yes</span></span>         |<span data-ttu-id="085d6-124">Sí</span><span class="sxs-lookup"><span data-stu-id="085d6-124">Yes</span></span>         |
|<span data-ttu-id="085d6-125">Administrador de servicios de Teams</span><span class="sxs-lookup"><span data-stu-id="085d6-125">Teams Service Administrator</span></span>     |<span data-ttu-id="085d6-126">Sí</span><span class="sxs-lookup"><span data-stu-id="085d6-126">Yes</span></span>         |<span data-ttu-id="085d6-127">Sí</span><span class="sxs-lookup"><span data-stu-id="085d6-127">Yes</span></span>         |<span data-ttu-id="085d6-128">Sí</span><span class="sxs-lookup"><span data-stu-id="085d6-128">Yes</span></span>         |<span data-ttu-id="085d6-129">Sí</span><span class="sxs-lookup"><span data-stu-id="085d6-129">Yes</span></span>         |
|<span data-ttu-id="085d6-130">Administrador de comunicaciones de Teams</span><span class="sxs-lookup"><span data-stu-id="085d6-130">Teams Communications Administrator</span></span>     |<span data-ttu-id="085d6-131">Sí</span><span class="sxs-lookup"><span data-stu-id="085d6-131">Yes</span></span>         |<span data-ttu-id="085d6-132">Sí</span><span class="sxs-lookup"><span data-stu-id="085d6-132">Yes</span></span>         |<span data-ttu-id="085d6-133">Sí</span><span class="sxs-lookup"><span data-stu-id="085d6-133">Yes</span></span>         |<span data-ttu-id="085d6-134">Sí</span><span class="sxs-lookup"><span data-stu-id="085d6-134">Yes</span></span>         |
|<span data-ttu-id="085d6-135">Ingeniero de soporte en comunicaciones de Teams</span><span class="sxs-lookup"><span data-stu-id="085d6-135">Teams Communications Support Engineer</span></span>     |<span data-ttu-id="085d6-136">Sí</span><span class="sxs-lookup"><span data-stu-id="085d6-136">Yes</span></span>         |<span data-ttu-id="085d6-137">Sí</span><span class="sxs-lookup"><span data-stu-id="085d6-137">Yes</span></span>         |<span data-ttu-id="085d6-138">Sí</span><span class="sxs-lookup"><span data-stu-id="085d6-138">Yes</span></span>         |<span data-ttu-id="085d6-139">No</span><span class="sxs-lookup"><span data-stu-id="085d6-139">No</span></span>         |
|<span data-ttu-id="085d6-140">Especialista de soporte de comunicaciones de Teams</span><span class="sxs-lookup"><span data-stu-id="085d6-140">Teams Communications Support Specialist</span></span>     |<span data-ttu-id="085d6-141">Sí</span><span class="sxs-lookup"><span data-stu-id="085d6-141">Yes</span></span>         |<span data-ttu-id="085d6-142">No</span><span class="sxs-lookup"><span data-stu-id="085d6-142">No</span></span>         |<span data-ttu-id="085d6-143">Sí</span><span class="sxs-lookup"><span data-stu-id="085d6-143">Yes</span></span>         |<span data-ttu-id="085d6-144">No</span><span class="sxs-lookup"><span data-stu-id="085d6-144">No</span></span>         |
|<span data-ttu-id="085d6-145">Administrador de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="085d6-145">Skype for Business Administrator</span></span>     |<span data-ttu-id="085d6-146">Sí</span><span class="sxs-lookup"><span data-stu-id="085d6-146">Yes</span></span>         |<span data-ttu-id="085d6-147">Sí</span><span class="sxs-lookup"><span data-stu-id="085d6-147">Yes</span></span>         |<span data-ttu-id="085d6-148">Sí</span><span class="sxs-lookup"><span data-stu-id="085d6-148">Yes</span></span>         |<span data-ttu-id="085d6-149">Sí</span><span class="sxs-lookup"><span data-stu-id="085d6-149">Yes</span></span>         |
|<span data-ttu-id="085d6-150">Lector global</span><span class="sxs-lookup"><span data-stu-id="085d6-150">Global Reader</span></span> |<span data-ttu-id="085d6-151">Sí</span><span class="sxs-lookup"><span data-stu-id="085d6-151">Yes</span></span>         |<span data-ttu-id="085d6-152">Sí</span><span class="sxs-lookup"><span data-stu-id="085d6-152">Yes</span></span>         |<span data-ttu-id="085d6-153">Sí</span><span class="sxs-lookup"><span data-stu-id="085d6-153">Yes</span></span>         |<span data-ttu-id="085d6-154">No</span><span class="sxs-lookup"><span data-stu-id="085d6-154">No</span></span>         |
|<span data-ttu-id="085d6-155">Lector de<sup>informes 1</sup></span><span class="sxs-lookup"><span data-stu-id="085d6-155">Reports Reader<sup>1</sup></span></span>     |<span data-ttu-id="085d6-156">Sí</span><span class="sxs-lookup"><span data-stu-id="085d6-156">Yes</span></span>         |<span data-ttu-id="085d6-157">No</span><span class="sxs-lookup"><span data-stu-id="085d6-157">No</span></span>         |<span data-ttu-id="085d6-158">Sí</span><span class="sxs-lookup"><span data-stu-id="085d6-158">Yes</span></span>         |<span data-ttu-id="085d6-159">No</span><span class="sxs-lookup"><span data-stu-id="085d6-159">No</span></span>         |

<span data-ttu-id="085d6-160"><sup>1</sup> Además de leer los informes del CQD, el Lector de informes puede ver todos los informes de actividad en el centro de administración y los informes del paquete de contenido Adopción de [Microsoft 365.](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f) [](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263)</span><span class="sxs-lookup"><span data-stu-id="085d6-160"><sup>1</sup> In addition to reading CQD reports, the Reports Reader can view all the [activity reports](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) in the admin center and any reports from the [Microsoft 365 Adoption content pack](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).</span></span>

> [!NOTE]
> <span data-ttu-id="085d6-161">Si no ve [EUII (información](CQD-data-and-reports.md#euii-data) de identificación del usuario final) y tiene una de las funciones a las que se permite ver esta información, tenga en cuenta que el CQD solo mantiene EUII durante 28 días.</span><span class="sxs-lookup"><span data-stu-id="085d6-161">If you're not seeing [EUII (end-user identifiable information)](CQD-data-and-reports.md#euii-data) and you have one of the roles that's permitted to see this information, keep in mind that CQD only keeps EUII for 28 days.</span></span> <span data-ttu-id="085d6-162">Se elimina cualquier cosa que sobresala más de 28 días.</span><span class="sxs-lookup"><span data-stu-id="085d6-162">Anything older than 28 days is deleted.</span></span>

<span data-ttu-id="085d6-163">Para obtener más información sobre estos roles, consulte [Acerca de los roles de administrador de Office 365.](/office365/admin/add-users/about-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="085d6-163">For more information about these roles, see [About Office 365 admin roles](/office365/admin/add-users/about-admin-roles).</span></span>


<span data-ttu-id="085d6-164">Después de iniciar sesión por primera vez, el CQD comenzará a recopilar y procesar datos.</span><span class="sxs-lookup"><span data-stu-id="085d6-164">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="085d6-165">A partir de diciembre de 2019, aún puede acceder a la versión anterior del CQD (cqd.lync.com), aunque el portal heredado le proporciona un vínculo al último CQD (cqd.teams.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="085d6-165">As of December 2019, you can still access the older version of CQD (cqd.lync.com), although the legacy portal gives you a link to the latest CQD (cqd.teams.microsoft.com).</span></span> <span data-ttu-id="085d6-166">Finalmente, se retirará la versión anterior del CQD.</span><span class="sxs-lookup"><span data-stu-id="085d6-166">Eventually, the older version of CQD will be decommissioned.</span></span> <span data-ttu-id="085d6-167">Desde el 1 de julio de 2020, la versión anterior del CQD accede a los datos del último CQD.</span><span class="sxs-lookup"><span data-stu-id="085d6-167">As of July 1, 2020, the older version of CQD accesses data from the latest CQD.</span></span>


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a><span data-ttu-id="085d6-168">Migrar datos e informes de creación de la versión anterior del CQD</span><span class="sxs-lookup"><span data-stu-id="085d6-168">Migrate building data and reports from previous version of CQD</span></span>

> [!IMPORTANT]
> <span data-ttu-id="085d6-169">A partir del 1 de julio de 2020, ya no puede migrar los datos de creación e informes desde el CQD antiguo ( https://CQD.lync.com) .</span><span class="sxs-lookup"><span data-stu-id="085d6-169">As of July 1, 2020, you can no longer migrate building data and reports from the old CQD (https://CQD.lync.com).</span></span> 



## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="085d6-170">Usar Power BI para analizar datos del CQD</span><span class="sxs-lookup"><span data-stu-id="085d6-170">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="085d6-171">Novedades de enero de 2020: Descargar plantillas de consulta [de Power BI para el CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="085d6-171">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="085d6-172">Las plantillas personalizables de Power BI que puede usar para analizar e informar sobre los datos del CQD.</span><span class="sxs-lookup"><span data-stu-id="085d6-172">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="085d6-173">Lea [Usar Power BI para analizar datos del CQD](CQD-Power-BI-query-templates.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="085d6-173">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>


## <a name="related-topics"></a><span data-ttu-id="085d6-174">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="085d6-174">Related topics</span></span>

[<span data-ttu-id="085d6-175">Mejorar y supervisar la calidad de las llamadas en Teams</span><span class="sxs-lookup"><span data-stu-id="085d6-175">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="085d6-176">¿Qué es el CQD?</span><span class="sxs-lookup"><span data-stu-id="085d6-176">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="085d6-177">Cargar datos de inquilino y de edificio</span><span class="sxs-lookup"><span data-stu-id="085d6-177">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="085d6-178">Informes y datos del CQD</span><span class="sxs-lookup"><span data-stu-id="085d6-178">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="085d6-179">Usar el CQD para administrar la calidad de las llamadas y las reuniones</span><span class="sxs-lookup"><span data-stu-id="085d6-179">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="085d6-180">Dimensiones y medidas disponibles en el CQD</span><span class="sxs-lookup"><span data-stu-id="085d6-180">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="085d6-181">Clasificación de transmisiones en el CQD</span><span class="sxs-lookup"><span data-stu-id="085d6-181">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="085d6-182">Usar Power BI para analizar datos del CQD</span><span class="sxs-lookup"><span data-stu-id="085d6-182">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)
