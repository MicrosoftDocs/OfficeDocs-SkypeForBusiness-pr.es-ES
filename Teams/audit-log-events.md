---
title: Buscar eventos en el registro de auditoría en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: Aprenda a recuperar datos de Microsoft Teams del registro de auditoría de Office 365.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 028d01a2ed05f3596cfe7cca299a1b8e35a15721
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32194995"
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="a866e-103">Buscar eventos en el registro de auditoría en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a866e-103">Search the audit log for events in Microsoft Teams</span></span>
==================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="a866e-104">El registro de auditoría puede ayudarle a investigar actividades específicas en los servicios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="a866e-104">The audit log can help you investigate specific activities across Office 365 services.</span></span> <span data-ttu-id="a866e-105">Estas son algunas de las actividades que se auditan en Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="a866e-105">For Teams, here are some of the activities that are audited:</span></span>

-   <span data-ttu-id="a866e-106">Creación de equipos</span><span class="sxs-lookup"><span data-stu-id="a866e-106">Team creation</span></span>

-   <span data-ttu-id="a866e-107">Eliminación de equipos</span><span class="sxs-lookup"><span data-stu-id="a866e-107">Team deletion</span></span>

-   <span data-ttu-id="a866e-108">Agregación de canales</span><span class="sxs-lookup"><span data-stu-id="a866e-108">Added channel</span></span>

-   <span data-ttu-id="a866e-109">Cambios en la configuración</span><span class="sxs-lookup"><span data-stu-id="a866e-109">Changed setting</span></span>

<span data-ttu-id="a866e-110">Para ver la lista completa de actividades auditadas en Office 365, consulte [Buscar en el registro de auditoría del Centro de seguridad y cumplimiento de Office 365](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).</span><span class="sxs-lookup"><span data-stu-id="a866e-110">To see the complete list of activities that are audited in Office 365, read [Search the audit log in the Office 365 Security & Compliance Center](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="turn-on-auditing-in-teams"></a><span data-ttu-id="a866e-111">Activar la auditoría en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a866e-111">Turn on auditing in Teams</span></span>

<span data-ttu-id="a866e-112">Antes de que puede buscar en los datos de auditoría, tiene que activar el primer de auditoría en el **& centro de cumplimiento de seguridad**(https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="a866e-112">Before you can look at audit data, you have to first turn on auditing in the **Security & Compliance Center**(https://protection.office.com).</span></span> <span data-ttu-id="a866e-113">Para obtener ayuda para activar la auditoría, consulte [Activar o desactivar la búsqueda de registros de auditoría de Office 365](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span><span class="sxs-lookup"><span data-stu-id="a866e-113">For help turning on auditing, read [Turn Office 365 audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="a866e-114">Los datos de auditoría solo están disponibles desde el momento en que se habilitó la auditoría.</span><span class="sxs-lookup"><span data-stu-id="a866e-114">Audit data is only available from the point at which you turned on Auditing.</span></span>



## <a name="retrieve-teams-data-from-the-audit-log"></a><span data-ttu-id="a866e-115">Recuperar datos de Microsoft Teams del registro de auditoría</span><span class="sxs-lookup"><span data-stu-id="a866e-115">Retrieve Teams data from the audit log</span></span>

1.  <span data-ttu-id="a866e-116">Para recuperar los registros de auditoría, vaya al [Centro de seguridad y cumplimiento](https://go.microsoft.com/fwlink/?linkid=855775).</span><span class="sxs-lookup"><span data-stu-id="a866e-116">To retrieve audit logs, go to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=855775).</span></span> <span data-ttu-id="a866e-117">En **Search & Investigation** (Búsqueda e investigación), seleccione **Audit log search** (Búsqueda en el registro de auditorías).![Captura de pantalla de la página de búsqueda del registro de auditorías del Centro de seguridad y cumplimiento.](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)</span><span class="sxs-lookup"><span data-stu-id="a866e-117">Under **Search & Investigation**, select **Audit log search**.![Screenshot of the Audit log search page of the Security & Compliance Center.](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)</span></span>

2.  <span data-ttu-id="a866e-118">Use **Buscar** para filtrar por las actividades, las fechas y los usuarios que desee auditar.</span><span class="sxs-lookup"><span data-stu-id="a866e-118">Use **Search** to filter by the activities, dates, and users you want to audit.</span></span>

3.  <span data-ttu-id="a866e-119">Exporte los resultados a Excel para continuar el análisis.</span><span class="sxs-lookup"><span data-stu-id="a866e-119">Export your results to Excel for further analysis.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="a866e-120">Los datos de auditoría solo están visibles en el registro de auditoría si está activada la auditoría.</span><span class="sxs-lookup"><span data-stu-id="a866e-120">Audit data is only visible in the Audit Log if auditing is turned on.</span></span>

## <a name="video-techtip-using-audit-log-search-in-teams"></a><span data-ttu-id="a866e-121">Vídeo: TechTip: Usar la búsqueda en el registro de auditoría en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a866e-121">Video: TechTip: Using Audit Log Search in Teams</span></span>

<span data-ttu-id="a866e-122">Observe cómo Ansuman Acharya, un director de proyectos de Microsoft Teams, realiza una búsqueda en el registro de auditoría para Microsoft Teams en el Centro de seguridad y cumplimiento de Office 365.</span><span class="sxs-lookup"><span data-stu-id="a866e-122">Join Ansuman Acharya, a program manager for Teams, as he demonstrates conducting an Audit Log search for Teams in the Office 365 Security & Compliance Center.</span></span> 


> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]






