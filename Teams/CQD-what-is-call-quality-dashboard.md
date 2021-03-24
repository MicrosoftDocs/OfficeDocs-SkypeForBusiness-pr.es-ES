---
title: ¿Qué es el Panel de calidad de llamadas (CQD)?
ms.author: serdars
author: SerdarSoysal
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
description: Obtenga información sobre el Panel de calidad de llamadas (CQD) y cómo usarlo para ver informes sobre la calidad de las reuniones y las llamadas en Microsoft Teams.
ms.openlocfilehash: c78e427ef87f7485932fac207c10add71c8bf269
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094944"
---
# <a name="what-is-call-quality-dashboard-cqd"></a><span data-ttu-id="19a1b-103">¿Qué es el Panel de calidad de llamadas (CQD)?</span><span class="sxs-lookup"><span data-stu-id="19a1b-103">What is Call Quality Dashboard (CQD)?</span></span>

<span data-ttu-id="19a1b-104">El Panel de calidad de llamadas de Microsoft (CQD): muestra la calidad de las llamadas y reuniones, a nivel de toda la [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) organización, para Microsoft Teams, Skype Empresarial Online y Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="19a1b-104">The Microsoft Call Quality Dashboard (CQD) - [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) - shows call and meeting quality, at an **org-wide level**, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

  
<span data-ttu-id="19a1b-105">La última versión de CQD incluye una fuente de datos en tiempo [casi real (NRT),](CQD-data-and-reports.md)lo que significa que los registros de llamadas están disponibles en CQD dentro de los 30 minutos adicionales al final de una llamada.</span><span class="sxs-lookup"><span data-stu-id="19a1b-105">The latest version of CQD features a [near-real-time (NRT) data feed](CQD-data-and-reports.md), which means that call records are available in CQD within 30 minutes of the end of a call.</span></span>

<span data-ttu-id="19a1b-106">Siempre que CQD incluya datos de identificación del usuario final [(EUII),](CQD-data-and-reports.md#euii-data)se administra de la misma manera que EUII en [Microsoft 365.](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)</span><span class="sxs-lookup"><span data-stu-id="19a1b-106">Wherever CQD includes [end-user identifiable information (EUII) data](CQD-data-and-reports.md#euii-data), it's managed in the same way as [EUII throughout Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

<span data-ttu-id="19a1b-107">CQD está diseñado para ayudar a administradores de Teams, administradores de Skype Empresarial e ingenieros de red a supervisar la calidad de las llamadas y reuniones a nivel de toda la organización.</span><span class="sxs-lookup"><span data-stu-id="19a1b-107">CQD is designed to help Teams admins, Skype for Business admins, and network engineers monitor call and meeting quality at an org-wide level.</span></span> <span data-ttu-id="19a1b-108">Usará CQD para ayudarle a optimizar **la red para** mejorar la calidad del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="19a1b-108">You'll use CQD to help you **optimize your network** to drive performance quality.</span></span> <span data-ttu-id="19a1b-109">Cuando necesite buscar información de llamada y reunión para un usuario **específico,** use los datos de CQD junto con el análisis de [llamadas por usuario.](use-call-analytics-to-troubleshoot-poor-call-quality.md)</span><span class="sxs-lookup"><span data-stu-id="19a1b-109">When you need to look into call and meeting information for a **specific user**, use CQD data in conjunction with per-user [call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>

<span data-ttu-id="19a1b-110">Por ejemplo, con CQD, puede determinar que la mala calidad de la llamada de un usuario (que observó con análisis de llamadas por usuario) se debe a un problema de red que también afecta a muchos otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="19a1b-110">For example, using CQD, you can determine that a user's poor call quality (which you observed using per-user call analytics) is due to a network issue that also affects many other users.</span></span> <span data-ttu-id="19a1b-111">CQD captura tanto la experiencia de llamada individual como la calidad general de las llamadas realizadas con Teams o Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="19a1b-111">CQD captures both the individual call experience and the overall quality of calls made using Teams or Skype for Business.</span></span> <span data-ttu-id="19a1b-112">Con CQD, los patrones generales pueden ser evidentes, por lo que los ingenieros de red pueden realizar evaluaciones fundamentadas de la calidad de las llamadas.</span><span class="sxs-lookup"><span data-stu-id="19a1b-112">With CQD, overall patterns may become apparent, so network engineers can make informed assessments of call quality.</span></span> <span data-ttu-id="19a1b-113">CQD proporciona informes de métricas de calidad de llamadas que le proporcionan información sobre la calidad general de las llamadas, las transmisiones de cliente-servidor, las transmisiones cliente-cliente y el SLA de calidad [de voz.](https://go.microsoft.com/fwlink/p/?linkid=846252)</span><span class="sxs-lookup"><span data-stu-id="19a1b-113">CQD provides reports of call quality metrics that give you insight into overall call quality, server-client streams, client-client streams, and voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span> 
  
![Captura de pantalla del panel de calidad de llamadas.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

<span data-ttu-id="19a1b-115">En CQD, le recomendamos que cargue información de creación y punto de conexión, lo que le permite usar Location-Enhanced Informes para analizar la calidad y la confiabilidad de las llamadas dentro del edificio de un usuario.</span><span class="sxs-lookup"><span data-stu-id="19a1b-115">In CQD, we encourage you to upload building and endpoint information, which lets you use Location-Enhanced Reports to analyze call quality and reliability within a user's building.</span></span> <span data-ttu-id="19a1b-116">Los datos se pueden evaluar para determinar si el problema está aislado para un solo usuario o afecta a un segmento más grande de usuarios.</span><span class="sxs-lookup"><span data-stu-id="19a1b-116">The data can be assessed to determine if the problem is isolated to a single user or affects a larger segment of users.</span></span> <span data-ttu-id="19a1b-117">Para activar la creación o las vistas específicas del [](CQD-upload-tenant-building-data.md) punto de conexión en CQD, un administrador debe cargar información de creación o punto de conexión en la página Carga de datos del inquilino CQD. </span><span class="sxs-lookup"><span data-stu-id="19a1b-117">To turn on building or endpoint-specific views in CQD, an admin must [upload building or endpoint information](CQD-upload-tenant-building-data.md) on the CQD **Tenant Data Upload** page.</span></span>

![Captura de pantalla del panel de calidad de Location-Enhanced llamadas.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

<span data-ttu-id="19a1b-119">No se pierda [](quality-of-experience-review-guide.md) nuestro artículo Administrar la calidad de las llamadas y reuniones, que ofrece instrucciones detalladas para el administrador de Teams o el ingeniero de soporte técnico responsable de administrar la calidad del servicio en Teams.</span><span class="sxs-lookup"><span data-stu-id="19a1b-119">Don't miss our [Manage call and meeting quality](quality-of-experience-review-guide.md) article, which offers in-depth guidance for the Teams admin or support engineer responsible for managing service quality in Teams.</span></span>

## <a name="older-version-of-cqd-cqdlynccom"></a><span data-ttu-id="19a1b-120">Versión anterior de CQD (CQD.lync.com)</span><span class="sxs-lookup"><span data-stu-id="19a1b-120">Older version of CQD (CQD.lync.com)</span></span>

<span data-ttu-id="19a1b-121">La versión actual de CQD ( reemplaza la https://CQD.Teams.microsoft.com) versión anterior de CQD ( https://CQD.lync.com) .</span><span class="sxs-lookup"><span data-stu-id="19a1b-121">The current version of CQD (https://CQD.Teams.microsoft.com) is replacing the older version of CQD (https://CQD.lync.com).</span></span> <span data-ttu-id="19a1b-122">Todavía puede usar CQD.lync.com (disponible en el Centro de administración de Skype Empresarial), pero a partir del 1 de julio de 2020, está usando los datos de CQD. Teams.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="19a1b-122">You can still use CQD.lync.com (available from the Skype for Business admin center), but as of July 1, 2020, it's using the data from CQD.Teams.microsoft.com.</span></span> <span data-ttu-id="19a1b-123">Desactivaremos el acceso a CQD.lync.com, por lo que deberías moverte a CQD. Teams.microsoft.com si aún no lo ha hecho.</span><span class="sxs-lookup"><span data-stu-id="19a1b-123">We'll turn off access to CQD.lync.com soon, so you should move to CQD.Teams.microsoft.com if you haven't already done so.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="19a1b-124">A partir del 1 de julio de 2020, ya no puede ver ni modificar los datos de creación o consulta desde el antiguo CQD (CQD.lync.com).</span><span class="sxs-lookup"><span data-stu-id="19a1b-124">As of July 1, 2020, you can no longer view or modify your building or query data from the old CQD (CQD.lync.com).</span></span> <span data-ttu-id="19a1b-125">Si aún no ha migrado estos datos desde CQD.lync.com y los sigue necesitando, registre un vale de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="19a1b-125">If you haven't already migrated this data from CQD.lync.com and still need it, log a support ticket.</span></span>

## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="19a1b-126">Usar Power BI para analizar datos CQD</span><span class="sxs-lookup"><span data-stu-id="19a1b-126">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="19a1b-127">Nuevo en enero de 2020: Descargar plantillas de consulta [de Power BI para CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="19a1b-127">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="19a1b-128">Plantillas de Power BI personalizables que puede usar para analizar e informar de los datos de CQD.</span><span class="sxs-lookup"><span data-stu-id="19a1b-128">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="19a1b-129">Lea [Usar Power BI para analizar datos CQD](CQD-Power-BI-query-templates.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="19a1b-129">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>



## <a name="related-topics"></a><span data-ttu-id="19a1b-130">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="19a1b-130">Related topics</span></span>

[<span data-ttu-id="19a1b-131">Mejorar y supervisar la calidad de las llamadas de Teams</span><span class="sxs-lookup"><span data-stu-id="19a1b-131">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="19a1b-132">Configurar el panel de calidad de llamadas (CQD)</span><span class="sxs-lookup"><span data-stu-id="19a1b-132">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="19a1b-133">Cargar datos de inquilino y creación</span><span class="sxs-lookup"><span data-stu-id="19a1b-133">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="19a1b-134">Datos e informes de CQD</span><span class="sxs-lookup"><span data-stu-id="19a1b-134">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="19a1b-135">Usar CQD para administrar la calidad de las llamadas y las reuniones</span><span class="sxs-lookup"><span data-stu-id="19a1b-135">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="19a1b-136">Dimensiones y medidas disponibles en CQD</span><span class="sxs-lookup"><span data-stu-id="19a1b-136">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="19a1b-137">Clasificación de secuencias en CQD</span><span class="sxs-lookup"><span data-stu-id="19a1b-137">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="19a1b-138">Usar Power BI para analizar datos CQD</span><span class="sxs-lookup"><span data-stu-id="19a1b-138">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)


[<span data-ttu-id="19a1b-139">Solución de problemas de Teams</span><span class="sxs-lookup"><span data-stu-id="19a1b-139">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)