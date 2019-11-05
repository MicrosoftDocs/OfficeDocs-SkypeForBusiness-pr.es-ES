---
title: Buscar eventos en el registro de auditoría en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: Aprenda a recuperar datos de Microsoft Teams del registro de auditoría de Office 365.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 96197e7acf067675f3468b122c6fcc8c0386c010
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2019
ms.locfileid: "37968021"
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="c79c0-103">Buscar eventos en el registro de auditoría en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c79c0-103">Search the audit log for events in Microsoft Teams</span></span>
==================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="c79c0-104">El registro de auditoría puede ayudarle a investigar actividades específicas en los servicios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="c79c0-104">The audit log can help you investigate specific activities across Office 365 services.</span></span> <span data-ttu-id="c79c0-105">Estas son algunas de las actividades que se auditan en Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="c79c0-105">For Teams, here are some of the activities that are audited:</span></span>

- <span data-ttu-id="c79c0-106">Creación de equipos</span><span class="sxs-lookup"><span data-stu-id="c79c0-106">Team creation</span></span>

- <span data-ttu-id="c79c0-107">Eliminación de equipos</span><span class="sxs-lookup"><span data-stu-id="c79c0-107">Team deletion</span></span>

- <span data-ttu-id="c79c0-108">Agregación de canales</span><span class="sxs-lookup"><span data-stu-id="c79c0-108">Added channel</span></span>

- <span data-ttu-id="c79c0-109">Cambios en la configuración</span><span class="sxs-lookup"><span data-stu-id="c79c0-109">Changed setting</span></span>

> [!NOTE]
> <span data-ttu-id="c79c0-110">Los eventos de auditoría de canales privados también se registran como si se trataran de equipos y canales estándar.</span><span class="sxs-lookup"><span data-stu-id="c79c0-110">Audit events from private channels are also logged as they are for teams and standard channels.</span></span>

<span data-ttu-id="c79c0-111">Para ver la lista completa de actividades auditadas en Office 365, consulte [Buscar en el registro de auditoría del Centro de seguridad y cumplimiento de Office 365](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).</span><span class="sxs-lookup"><span data-stu-id="c79c0-111">To see the complete list of activities that are audited in Office 365, read [Search the audit log in the Office 365 Security & Compliance Center](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="turn-on-auditing-in-teams"></a><span data-ttu-id="c79c0-112">Activar la auditoría en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c79c0-112">Turn on auditing in Teams</span></span>

<span data-ttu-id="c79c0-113">Para poder consultar los datos de auditoría, primero debe activar la auditoría en el [centro de cumplimiento de & de seguridad](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="c79c0-113">Before you can look at audit data, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="c79c0-114">Para obtener ayuda para activar la auditoría, consulte [Activar o desactivar la búsqueda de registros de auditoría de Office 365](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span><span class="sxs-lookup"><span data-stu-id="c79c0-114">For help turning on auditing, read [Turn Office 365 audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c79c0-115">Los datos de auditoría solo están disponibles desde el momento en que se habilitó la auditoría.</span><span class="sxs-lookup"><span data-stu-id="c79c0-115">Audit data is only available from the point at which you turned on Auditing.</span></span>

## <a name="retrieve-teams-data-from-the-audit-log"></a><span data-ttu-id="c79c0-116">Recuperar datos de Microsoft Teams del registro de auditoría</span><span class="sxs-lookup"><span data-stu-id="c79c0-116">Retrieve Teams data from the audit log</span></span>

1. <span data-ttu-id="c79c0-117">Para recuperar los registros de auditoría, vaya al [Centro de seguridad y cumplimiento](https://go.microsoft.com/fwlink/?linkid=855775).</span><span class="sxs-lookup"><span data-stu-id="c79c0-117">To retrieve audit logs, go to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=855775).</span></span> <span data-ttu-id="c79c0-118">En **buscar & investigación**, seleccione **búsqueda de registros de auditoría**.</span><span class="sxs-lookup"><span data-stu-id="c79c0-118">Under **Search & Investigation**, select **Audit log search**.</span></span>

2. <span data-ttu-id="c79c0-119">Use **Buscar** para filtrar por las actividades, las fechas y los usuarios que desee auditar.</span><span class="sxs-lookup"><span data-stu-id="c79c0-119">Use **Search** to filter by the activities, dates, and users you want to audit.</span></span>

3. <span data-ttu-id="c79c0-120">Exporte los resultados a Excel para continuar el análisis.</span><span class="sxs-lookup"><span data-stu-id="c79c0-120">Export your results to Excel for further analysis.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c79c0-121">Los datos de auditoría solo están visibles en el registro de auditoría si está activada la auditoría.</span><span class="sxs-lookup"><span data-stu-id="c79c0-121">Audit data is only visible in the Audit Log if auditing is turned on.</span></span>

## <a name="video-techtip-using-audit-log-search-in-teams"></a><span data-ttu-id="c79c0-122">Vídeo: TechTip: Usar la búsqueda en el registro de auditoría en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c79c0-122">Video: TechTip: Using Audit Log Search in Teams</span></span>

<span data-ttu-id="c79c0-123">Observe cómo Ansuman Acharya, un director de proyectos de Microsoft Teams, realiza una búsqueda en el registro de auditoría para Microsoft Teams en el Centro de seguridad y cumplimiento de Office 365.</span><span class="sxs-lookup"><span data-stu-id="c79c0-123">Join Ansuman Acharya, a program manager for Teams, as he demonstrates conducting an Audit Log search for Teams in the Office 365 Security & Compliance Center.</span></span> 

> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]
