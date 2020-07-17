---
title: ¿Qué es el panel de calidad de llamadas (CQD)?
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
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
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Obtenga más información sobre el panel de calidad de llamadas (CQD) y cómo usarlo para ver informes de calidad de llamadas y reuniones en Microsoft Teams.
ms.openlocfilehash: b7830d60139991b7ccc18679af798c74430e8ed1
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "45088248"
---
# <a name="what-is-call-quality-dashboard-cqd"></a><span data-ttu-id="d3aed-103">¿Qué es el panel de calidad de llamadas (CQD)?</span><span class="sxs-lookup"><span data-stu-id="d3aed-103">What is Call Quality Dashboard (CQD)?</span></span>

<span data-ttu-id="d3aed-104">El panel de calidad de llamadas de Microsoft (CQD) muestra la calidad de las [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) llamadas y reuniones, en **el nivel de toda la organización**, de Microsoft Teams, Skype empresarial online y skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d3aed-104">The Microsoft Call Quality Dashboard (CQD) - [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) - shows call and meeting quality, at an **org-wide level**, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

  
<span data-ttu-id="d3aed-105">La última versión del CQD incluye una [fuente de datos casi-real (NRT)](CQD-data-and-reports.md), lo que significa que los registros de llamadas están disponibles en el CQD en un plazo de 30 minutos a partir de la finalización de una llamada.</span><span class="sxs-lookup"><span data-stu-id="d3aed-105">The latest version of CQD features a [near-real-time (NRT) data feed](CQD-data-and-reports.md), which means that call records are available in CQD within 30 minutes of the end of a call.</span></span>

<span data-ttu-id="d3aed-106">Dondequiera que el CQD incluya [datos de identificación de usuario final (EUII)](CQD-data-and-reports.md#euii-data), se administra de la misma manera que [EUII en Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span><span class="sxs-lookup"><span data-stu-id="d3aed-106">Wherever CQD includes [end-user identifiable information (EUII) data](CQD-data-and-reports.md#euii-data), it's managed in the same way as [EUII throughout Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

<span data-ttu-id="d3aed-107">El CQD está diseñado para ayudar a los administradores de equipos, administradores de Skype empresarial e ingenieros de redes a supervisar la calidad de las llamadas y la reunión en el nivel de toda la organización.</span><span class="sxs-lookup"><span data-stu-id="d3aed-107">CQD is designed to help Teams admins, Skype for Business admins, and network engineers monitor call and meeting quality at an org-wide level.</span></span> <span data-ttu-id="d3aed-108">Deberá usar el CQD para ayudarle a **optimizar su red** y así controlar la calidad de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="d3aed-108">You'll use CQD to help you **optimize your network** to drive performance quality.</span></span> <span data-ttu-id="d3aed-109">Si necesita buscar información sobre las llamadas y la reunión de un **usuario específico**, use los datos del CQD junto con el [análisis de llamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md)por usuario.</span><span class="sxs-lookup"><span data-stu-id="d3aed-109">When you need to look into call and meeting information for a **specific user**, use CQD data in conjunction with per-user [call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>

<span data-ttu-id="d3aed-110">Por ejemplo, con el CQD, puede determinar que la mala calidad de las llamadas de un usuario (que usted ha observado mediante análisis de llamadas por usuario) se deba a un problema de red que también afecta a muchos otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="d3aed-110">For example, using CQD, you can determine that a user's poor call quality (which you observed using per-user call analytics) is due to a network issue that also affects many other users.</span></span> <span data-ttu-id="d3aed-111">El CQD captura tanto la experiencia de llamada individual como la calidad general de las llamadas hechas con Teams o Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="d3aed-111">CQD captures both the individual call experience and the overall quality of calls made using Teams or Skype for Business.</span></span> <span data-ttu-id="d3aed-112">Con el CQD, los patrones generales pueden ser aparentes, por lo que los ingenieros de red pueden realizar evaluaciones informadas de la calidad de las llamadas.</span><span class="sxs-lookup"><span data-stu-id="d3aed-112">With CQD, overall patterns may become apparent, so network engineers can make informed assessments of call quality.</span></span> <span data-ttu-id="d3aed-113">El CQD proporciona informes de métricas de calidad de llamadas que proporcionan una perspectiva de la calidad general de las llamadas, las secuencias de clientes de servidor, las secuencias de clientes cliente y los [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)de calidad de voz.</span><span class="sxs-lookup"><span data-stu-id="d3aed-113">CQD provides reports of call quality metrics that give you insight into overall call quality, server-client streams, client-client streams, and voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span> 
  
![Captura de pantalla del panel de calidad de llamadas.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

<span data-ttu-id="d3aed-115">En el CQD, le recomendamos que cargue la información de compilación y finalización, lo que le permite usar informes con ubicación mejorada para analizar la calidad de las llamadas y la confiabilidad dentro del edificio de un usuario.</span><span class="sxs-lookup"><span data-stu-id="d3aed-115">In CQD, we encourage you to upload building and endpoint information, which lets you use Location-Enhanced Reports to analyze call quality and reliability within a user's building.</span></span> <span data-ttu-id="d3aed-116">Los datos se pueden evaluar para determinar si el problema se aísla para un solo usuario o afecta a un segmento de usuarios más grande.</span><span class="sxs-lookup"><span data-stu-id="d3aed-116">The data can be assessed to determine if the problem is isolated to a single user or affects a larger segment of users.</span></span> <span data-ttu-id="d3aed-117">Para activar las vistas de creación o específicas de extremos en el CQD, un administrador debe [cargar la información de compilación o de extremo](CQD-upload-tenant-building-data.md) en la página de carga de datos del **inquilino** de CQD.</span><span class="sxs-lookup"><span data-stu-id="d3aed-117">To turn on building or endpoint-specific views in CQD, an admin must [upload building or endpoint information](CQD-upload-tenant-building-data.md) on the CQD **Tenant Data Upload** page.</span></span>

![Captura de pantalla de la ubicación del panel de calidad de llamadas: informes mejorados.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

<span data-ttu-id="d3aed-119">No pierdas nuestro artículo de [calidad de llamadas y reuniones de administración](quality-of-experience-review-guide.md) , que ofrece una guía detallada para el administrador o el ingeniero de soporte técnico de equipos responsable de administrar la calidad de los servicios en Teams.</span><span class="sxs-lookup"><span data-stu-id="d3aed-119">Don't miss our [Manage call and meeting quality](quality-of-experience-review-guide.md) article, which offers in-depth guidance for the Teams admin or support engineer responsible for managing service quality in Teams.</span></span>

## <a name="older-version-of-cqd-cqdlynccom"></a><span data-ttu-id="d3aed-120">Versión anterior del CQD (CQD.lync.com)</span><span class="sxs-lookup"><span data-stu-id="d3aed-120">Older version of CQD (CQD.lync.com)</span></span>

<span data-ttu-id="d3aed-121">La versión actual del CQD ( https://CQD.Teams.microsoft.com) está reemplazando la versión anterior del CQD ( https://CQD.lync.com) .</span><span class="sxs-lookup"><span data-stu-id="d3aed-121">The current version of CQD (https://CQD.Teams.microsoft.com) is replacing the older version of CQD (https://CQD.lync.com).</span></span> <span data-ttu-id="d3aed-122">Puede seguir usando CQD.lync.com (disponible en el centro de administración de Skype empresarial) pero, a partir del 1 de julio de 2020, está usando los datos del CQD. Teams.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="d3aed-122">You can still use CQD.lync.com (available from the Skype for Business admin center), but as of July 1, 2020, it's using the data from CQD.Teams.microsoft.com.</span></span> <span data-ttu-id="d3aed-123">Desactivaremos el acceso a CQD.lync.com pronto, por lo que debes ir a CQD. Teams.microsoft.com si aún no lo has hecho.</span><span class="sxs-lookup"><span data-stu-id="d3aed-123">We'll turn off access to CQD.lync.com soon, so you should move to CQD.Teams.microsoft.com if you haven't already done so.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d3aed-124">A partir del 1 de julio de 2020, ya no podrá ver ni modificar los datos de compilación o consulta del CQD anterior (CQD.lync.com).</span><span class="sxs-lookup"><span data-stu-id="d3aed-124">As of July 1, 2020, you can no longer view or modify your building or query data from the old CQD (CQD.lync.com).</span></span> <span data-ttu-id="d3aed-125">Si todavía no ha migrado los datos de CQD.lync.com y sigue siendo necesario, registre un vale de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="d3aed-125">If you haven't already migrated this data from CQD.lync.com and still need it, log a support ticket.</span></span>

## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="d3aed-126">Usar Power BI para analizar los datos del CQD</span><span class="sxs-lookup"><span data-stu-id="d3aed-126">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="d3aed-127">Novedades de enero de 2020: [Descargue las plantillas de consulta de Power BI para el CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="d3aed-127">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="d3aed-128">Plantillas de Power BI personalizables que puede usar para analizar y notificar los datos de CQD.</span><span class="sxs-lookup"><span data-stu-id="d3aed-128">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="d3aed-129">Leer [use Power BI para analizar los datos del CQD](CQD-Power-BI-query-templates.md) y obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d3aed-129">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>



## <a name="related-topics"></a><span data-ttu-id="d3aed-130">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d3aed-130">Related topics</span></span>

[<span data-ttu-id="d3aed-131">Mejorar y supervisar la calidad de las llamadas de los equipos</span><span class="sxs-lookup"><span data-stu-id="d3aed-131">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="d3aed-132">Configurar el panel de calidad de llamadas (CQD)</span><span class="sxs-lookup"><span data-stu-id="d3aed-132">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="d3aed-133">Cargar inquilino y datos de compilación</span><span class="sxs-lookup"><span data-stu-id="d3aed-133">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="d3aed-134">Datos e informes del CQD</span><span class="sxs-lookup"><span data-stu-id="d3aed-134">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="d3aed-135">Usar el CQD para administrar la calidad de las llamadas y reuniones</span><span class="sxs-lookup"><span data-stu-id="d3aed-135">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="d3aed-136">Dimensiones y medidas disponibles en el CQD</span><span class="sxs-lookup"><span data-stu-id="d3aed-136">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="d3aed-137">Clasificación de flujo en el CQD</span><span class="sxs-lookup"><span data-stu-id="d3aed-137">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="d3aed-138">Usar Power BI para analizar los datos del CQD</span><span class="sxs-lookup"><span data-stu-id="d3aed-138">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)


[<span data-ttu-id="d3aed-139">Solución de problemas de Teams</span><span class="sxs-lookup"><span data-stu-id="d3aed-139">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)