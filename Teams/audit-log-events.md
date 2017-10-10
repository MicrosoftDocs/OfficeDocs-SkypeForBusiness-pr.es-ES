---
title: "Buscar eventos en el log de auditorías en Microsoft Teams | Soporte técnico de Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Aprenda a recuperar datos de Microsoft Teams del registro de auditorías."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 558db88d32229fcaef70ea5278d7437fbea92198
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2017
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="f536c-103">Buscar eventos en el log de auditorías en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f536c-103">Search the audit log for events in Microsoft Teams</span></span>
==================================================

<span data-ttu-id="f536c-p101">El registro de auditorías ofrece capacidades de búsqueda ad-hoc en eventos destacados en todos los servicios de Office 365. Concretamente para Microsoft Teams, aquí hay algunos ejemplos de los eventos capturados:</span><span class="sxs-lookup"><span data-stu-id="f536c-p101">The Audit Log provides ad-hoc search capabilities into notable events across Office 365 services. For Microsoft Teams specifically, below are a few examples of events captured:</span></span>

-   <span data-ttu-id="f536c-106">Creación de equipos</span><span class="sxs-lookup"><span data-stu-id="f536c-106">Team Creation</span></span>

-   <span data-ttu-id="f536c-107">Eliminación de equipos</span><span class="sxs-lookup"><span data-stu-id="f536c-107">Team Deletion</span></span>

-   <span data-ttu-id="f536c-108">Canal agregado</span><span class="sxs-lookup"><span data-stu-id="f536c-108">Added Channel</span></span>

-   <span data-ttu-id="f536c-109">Configuración cambiada</span><span class="sxs-lookup"><span data-stu-id="f536c-109">Changed Setting</span></span>

<span data-ttu-id="f536c-110">La lista de eventos completa de todo Office 365 es muy larga y puede verla [aquí](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c?ui=en-US&rs=en-US&ad=US#ID0EABAAA=Audited_activities).</span><span class="sxs-lookup"><span data-stu-id="f536c-110">The complete event list across Office 365 is quite extensive and can be found [here](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c?ui=en-US&rs=en-US&ad=US#ID0EABAAA=Audited_activities).</span></span>

<span data-ttu-id="f536c-p102">Antes de profundizar en la información esencial sobre auditorías, debe habilitarlas. Para habilitar las auditorías, navegue a *Security & Compliance Admin Center* (Centro de administración de seguridad y cumplimiento). En *Search for activity* (Buscar actividad), haga clic en **Start recording now** (Iniciar grabación ahora). Transcurridas 24 horas, los datos de auditoría estarán disponibles a través de *Audit Log Search* (Búsqueda en el registro de auditorías) que se encuentra en la ficha *Search & Investigation* (Búsqueda e investigación).</span><span class="sxs-lookup"><span data-stu-id="f536c-p102">Before you can dig into audit insights, auditing must first be enabled. To enable Auditing, navigate to the *Security & Compliance* Admin Center. Under *Search for activity*, click on **Start recording now**. After 24hrs, audit data will be available via *Audit Log Search* located under the *Search & Investigation* tab.</span></span>


| |  |
|---------|---------|
|![](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image1.png)<br></br><span data-ttu-id="f536c-115">Importante</span><span class="sxs-lookup"><span data-stu-id="f536c-115">Important</span></span>     |<span data-ttu-id="f536c-116">Los datos de auditoría solo están disponibles desde el momento en que se habilitó la auditoría.</span><span class="sxs-lookup"><span data-stu-id="f536c-116">Audit data is only available from the point at which Auditing was enabled.</span></span>         |

![](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image2.png)

<span data-ttu-id="f536c-117">Veamos cómo recuperar datos de Microsoft Teams del registro de auditorías:</span><span class="sxs-lookup"><span data-stu-id="f536c-117">Now, let’s look at how to retrieve Microsoft Teams data from the Audit Log:</span></span>

1.  <span data-ttu-id="f536c-p103">Para recuperar información del registro de auditorías, navegue a [Security & Compliance Admin Center (Centro de administración de seguridad y cumplimiento)](https://go.microsoft.com/fwlink/?linkid=855775). En *Search & Investigation* (Búsqueda e investigación), seleccione **Audit log search** (Búsqueda en el registro de auditorías).</span><span class="sxs-lookup"><span data-stu-id="f536c-p103">To retrieve Audit Log information, navigate to the [Security & Compliance Admin Center](https://go.microsoft.com/fwlink/?linkid=855775). Under *Search & Investigation*, select **Audit log search.**</span></span>

    <span data-ttu-id="f536c-p104">a.  Microsoft Teams ha definido las actividades de auditoría que se pueden seleccionar como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="f536c-p104">a.  Microsoft Teams has defined audit activities that can be selected as shown below.</span></span>

![](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)

2.  <span data-ttu-id="f536c-p105">Tras seleccionar las actividades de interés, indique un intervalo de fechas y los usuarios de los que se recuperará información en Microsoft Teams. Haga clic en **Buscar** para obtener resultados.</span><span class="sxs-lookup"><span data-stu-id="f536c-p105">After selecting the activities of interest, supply a date range and users to retrieve Microsoft Teams information from. Click **Search** to retrieve the results.</span></span>

3.  <span data-ttu-id="f536c-124">Esta información se puede exportar a Excel y filtrarla si es necesario.</span><span class="sxs-lookup"><span data-stu-id="f536c-124">This information can be exported to Excel and filtered as needed.</span></span>


|  | |
|---------|---------|
|![](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image1.png)<br></br><span data-ttu-id="f536c-125">Importante</span><span class="sxs-lookup"><span data-stu-id="f536c-125">Important</span></span> |<span data-ttu-id="f536c-126">Si no se han habilitado las auditorías con antelación, deberá hacerlo antes de que los datos aparezcan en el registro de auditorías.</span><span class="sxs-lookup"><span data-stu-id="f536c-126">If auditing has not been enabled previously, that needs to be enabled before data will appear in the Audit Log.</span></span>         |
