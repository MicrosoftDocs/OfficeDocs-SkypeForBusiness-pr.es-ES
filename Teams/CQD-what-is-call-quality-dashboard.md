---
title: ¿Qué es el panel de calidad de llamadas??
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
description: Obtenga información sobre el panel de calidad de llamadas y cómo usarlo para ver informes sobre la calidad de las llamadas y reuniones en Microsoft Teams.
ms.openlocfilehash: 9ba1956533887314a9ffa7ad994cbb4c81ffe103
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583489"
---
# <a name="what-is-call-quality-dashboard-cqd"></a><span data-ttu-id="1838b-103">¿Qué es el panel de calidad de llamadas??</span><span class="sxs-lookup"><span data-stu-id="1838b-103">What is Call Quality Dashboard (CQD)?</span></span>

<span data-ttu-id="1838b-104">Panel de calidad de llamadas de Microsoft (CQD): muestra la calidad de las llamadas y reuniones, a nivel de toda la organización, para Microsoft Teams, Skype Empresarial Online y [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) Skype Empresarial Server 2019. </span><span class="sxs-lookup"><span data-stu-id="1838b-104">The Microsoft Call Quality Dashboard (CQD) - [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) - shows call and meeting quality, at an **org-wide level**, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

  
<span data-ttu-id="1838b-105">La última versión del CQD cuenta con una fuente de datos en tiempo [casi real (NRT),](CQD-data-and-reports.md)lo que significa que los registros de llamadas están disponibles en el CQD en un plazo de 30 minutos desde el final de una llamada.</span><span class="sxs-lookup"><span data-stu-id="1838b-105">The latest version of CQD features a [near-real-time (NRT) data feed](CQD-data-and-reports.md), which means that call records are available in CQD within 30 minutes of the end of a call.</span></span>

<span data-ttu-id="1838b-106">Siempre que el CQD incluya datos de identificación [(EUII)](CQD-data-and-reports.md#euii-data)del usuario final, se administra de la misma manera que [EUII en todo Microsoft 365.](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)</span><span class="sxs-lookup"><span data-stu-id="1838b-106">Wherever CQD includes [end-user identifiable information (EUII) data](CQD-data-and-reports.md#euii-data), it's managed in the same way as [EUII throughout Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

<span data-ttu-id="1838b-107">El CQD está diseñado para ayudar a los administradores de Teams, administradores de Skype Empresarial e ingenieros de red a supervisar la calidad de las llamadas y reuniones a nivel de toda la organización.</span><span class="sxs-lookup"><span data-stu-id="1838b-107">CQD is designed to help Teams admins, Skype for Business admins, and network engineers monitor call and meeting quality at an org-wide level.</span></span> <span data-ttu-id="1838b-108">Usará el CQD para ayudarle a **optimizar la red para** mejorar la calidad del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="1838b-108">You'll use CQD to help you **optimize your network** to drive performance quality.</span></span> <span data-ttu-id="1838b-109">Cuando necesite buscar información de llamadas y reuniones de un usuario **específico,** use los datos del CQD junto con el análisis de llamadas [por usuario.](use-call-analytics-to-troubleshoot-poor-call-quality.md)</span><span class="sxs-lookup"><span data-stu-id="1838b-109">When you need to look into call and meeting information for a **specific user**, use CQD data in conjunction with per-user [call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>

<span data-ttu-id="1838b-110">Por ejemplo, con el CQD, puede determinar que la mala calidad de llamada de un usuario (lo que observó mediante análisis de llamadas por usuario) se debe a un problema de red que también afecta a muchos otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="1838b-110">For example, using CQD, you can determine that a user's poor call quality (which you observed using per-user call analytics) is due to a network issue that also affects many other users.</span></span> <span data-ttu-id="1838b-111">El CQD captura tanto la experiencia de llamadas individuales como la calidad general de las llamadas realizadas con Teams o Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="1838b-111">CQD captures both the individual call experience and the overall quality of calls made using Teams or Skype for Business.</span></span> <span data-ttu-id="1838b-112">Con el CQD, pueden ser evidentes los patrones generales, por lo que los ingenieros de red pueden realizar evaluaciones informadas de la calidad de la llamada.</span><span class="sxs-lookup"><span data-stu-id="1838b-112">With CQD, overall patterns may become apparent, so network engineers can make informed assessments of call quality.</span></span> <span data-ttu-id="1838b-113">El CQD proporciona informes de métricas de calidad de llamadas que ofrecen información sobre la calidad general de las llamadas, las transmisiones de cliente-servidor, las transmisiones cliente-cliente y el SLA de calidad de [voz.](https://go.microsoft.com/fwlink/p/?linkid=846252)</span><span class="sxs-lookup"><span data-stu-id="1838b-113">CQD provides reports of call quality metrics that give you insight into overall call quality, server-client streams, client-client streams, and voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span> 
  
![Captura de pantalla del panel de calidad de llamadas.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

<span data-ttu-id="1838b-115">En el CQD, se recomienda cargar información de creación y punto de conexión, que le permite usar Location-Enhanced Reports para analizar la calidad y la confiabilidad de las llamadas en el edificio de un usuario.</span><span class="sxs-lookup"><span data-stu-id="1838b-115">In CQD, we encourage you to upload building and endpoint information, which lets you use Location-Enhanced Reports to analyze call quality and reliability within a user's building.</span></span> <span data-ttu-id="1838b-116">Los datos se pueden evaluar para determinar si el problema está aislado para un solo usuario o afecta a un segmento más grande de usuarios.</span><span class="sxs-lookup"><span data-stu-id="1838b-116">The data can be assessed to determine if the problem is isolated to a single user or affects a larger segment of users.</span></span> <span data-ttu-id="1838b-117">Para activar la creación o las vistas específicas del [](CQD-upload-tenant-building-data.md) punto de conexión en el CQD, un administrador debe cargar la información de edificio o punto de conexión en la página Carga de datos del inquilino del CQD. </span><span class="sxs-lookup"><span data-stu-id="1838b-117">To turn on building or endpoint-specific views in CQD, an admin must [upload building or endpoint information](CQD-upload-tenant-building-data.md) on the CQD **Tenant Data Upload** page.</span></span>

![Captura de pantalla de los informes de calidad de Location-Enhanced llamadas.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

<span data-ttu-id="1838b-119">No se pierda [](quality-of-experience-review-guide.md) nuestro artículo Administrar la calidad de las llamadas y las reuniones, que ofrece instrucciones detalladas para el administrador de Teams o el ingeniero de soporte técnico responsable de administrar la calidad del servicio en Teams.</span><span class="sxs-lookup"><span data-stu-id="1838b-119">Don't miss our [Manage call and meeting quality](quality-of-experience-review-guide.md) article, which offers in-depth guidance for the Teams admin or support engineer responsible for managing service quality in Teams.</span></span>

## <a name="older-version-of-cqd-cqdlynccom"></a><span data-ttu-id="1838b-120">Versión anterior del CQD (CQD.lync.com)</span><span class="sxs-lookup"><span data-stu-id="1838b-120">Older version of CQD (CQD.lync.com)</span></span>

<span data-ttu-id="1838b-121">La versión actual del CQD ( https://CQD.Teams.microsoft.com) está reemplazando la versión anterior del CQD ( https://CQD.lync.com) .</span><span class="sxs-lookup"><span data-stu-id="1838b-121">The current version of CQD (https://CQD.Teams.microsoft.com) is replacing the older version of CQD (https://CQD.lync.com).</span></span> <span data-ttu-id="1838b-122">Aún puede usar CQD.lync.com (disponible en el Centro de administración de Skype Empresarial), pero a partir del 1 de julio de 2020 está usando los datos del CQD. Teams.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="1838b-122">You can still use CQD.lync.com (available from the Skype for Business admin center), but as of July 1, 2020, it's using the data from CQD.Teams.microsoft.com.</span></span> <span data-ttu-id="1838b-123">Desactivaremos el acceso a CQD.lync.com, por lo que debes moverte al CQD. Teams.microsoft.com si aún no lo ha hecho.</span><span class="sxs-lookup"><span data-stu-id="1838b-123">We'll turn off access to CQD.lync.com soon, so you should move to CQD.Teams.microsoft.com if you haven't already done so.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1838b-124">Desde el 1 de julio de 2020, ya no puede ver ni modificar los datos de creación o consulta desde el CQD antiguo (CQD.lync.com).</span><span class="sxs-lookup"><span data-stu-id="1838b-124">As of July 1, 2020, you can no longer view or modify your building or query data from the old CQD (CQD.lync.com).</span></span> <span data-ttu-id="1838b-125">Si aún no ha migrado estos datos de CQD.lync.com aún los necesita, inicie sesión en una vale de soporte.</span><span class="sxs-lookup"><span data-stu-id="1838b-125">If you haven't already migrated this data from CQD.lync.com and still need it, log a support ticket.</span></span>

## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="1838b-126">Usar Power BI para analizar datos del CQD</span><span class="sxs-lookup"><span data-stu-id="1838b-126">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="1838b-127">Novedades de enero de 2020: Descargar plantillas de consulta [de Power BI para el CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="1838b-127">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="1838b-128">Plantillas personalizables de Power BI que puede usar para analizar e informar sobre los datos del CQD.</span><span class="sxs-lookup"><span data-stu-id="1838b-128">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="1838b-129">Lea [Usar Power BI para analizar datos del CQD](CQD-Power-BI-query-templates.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="1838b-129">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>



## <a name="related-topics"></a><span data-ttu-id="1838b-130">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="1838b-130">Related topics</span></span>

[<span data-ttu-id="1838b-131">Mejorar y supervisar la calidad de las llamadas en Teams</span><span class="sxs-lookup"><span data-stu-id="1838b-131">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="1838b-132">Configurar el panel de calidad de llamadas (CQD)</span><span class="sxs-lookup"><span data-stu-id="1838b-132">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="1838b-133">Cargar datos de inquilino y de edificio</span><span class="sxs-lookup"><span data-stu-id="1838b-133">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="1838b-134">Informes y datos del CQD</span><span class="sxs-lookup"><span data-stu-id="1838b-134">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="1838b-135">Usar el CQD para administrar la calidad de las llamadas y las reuniones</span><span class="sxs-lookup"><span data-stu-id="1838b-135">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="1838b-136">Dimensiones y medidas disponibles en el CQD</span><span class="sxs-lookup"><span data-stu-id="1838b-136">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="1838b-137">Clasificación de transmisiones en el CQD</span><span class="sxs-lookup"><span data-stu-id="1838b-137">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="1838b-138">Usar Power BI para analizar datos del CQD</span><span class="sxs-lookup"><span data-stu-id="1838b-138">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)


[<span data-ttu-id="1838b-139">Solución de problemas de Teams</span><span class="sxs-lookup"><span data-stu-id="1838b-139">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)