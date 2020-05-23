---
title: Ejecutar un informe para mostrar el uso de StaffHub activo
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Obtenga información sobre cómo ejecutar un informe para obtener una lista de los usuarios activos de StaffHub en su organización.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5701e508440a338e0f0ba1fd133dac98ec35d57f
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2020
ms.locfileid: "44349634"
---
# <a name="run-a-report-to-show-active-staffhub-usage"></a><span data-ttu-id="61dbf-103">Ejecutar un informe para mostrar el uso de StaffHub activo</span><span class="sxs-lookup"><span data-stu-id="61dbf-103">Run a report to show active StaffHub usage</span></span>

> [!IMPORTANT]
> <span data-ttu-id="61dbf-104">A partir del 30 de junio de 2020, Microsoft StaffHub se retirará.</span><span class="sxs-lookup"><span data-stu-id="61dbf-104">Effective June 30, 2020, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="61dbf-105">Estamos construyendo las capacidades de StaffHub en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="61dbf-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="61dbf-106">En la actualidad, Teams incluye la aplicación de turnos para la administración de la programación, y las funciones adicionales se aplicarán a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="61dbf-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="61dbf-107">StaffHub dejará de funcionar para todos los usuarios el 30 de junio de 2020.</span><span class="sxs-lookup"><span data-stu-id="61dbf-107">StaffHub will stop working for all users on June 30, 2020.</span></span> <span data-ttu-id="61dbf-108">Cualquier persona que intente abrir StaffHub recibirá un mensaje para que pueda descargar Teams.</span><span class="sxs-lookup"><span data-stu-id="61dbf-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="61dbf-109">Para obtener más información, consulte [Microsoft StaffHub para que se retirará](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="61dbf-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="61dbf-110">Siga los pasos descritos en este artículo para ejecutar un informe para obtener una lista de los usuarios activos de StaffHub de su organización.</span><span class="sxs-lookup"><span data-stu-id="61dbf-110">Use the steps in this article to run a report to get a list of active StaffHub users in your organization.</span></span> <span data-ttu-id="61dbf-111">Esta información puede resultar útil cuando se prepara para [mover los equipos de StaffHub a Microsoft Teams](move-staffhub-teams-to-shifts-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="61dbf-111">This information may come in handy when you prepare to [move your StaffHub teams to Microsoft Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span> <span data-ttu-id="61dbf-112">En el informe, sabrá quién tiene que incluir en las comunicaciones al cambiar de StaffHub a teams.</span><span class="sxs-lookup"><span data-stu-id="61dbf-112">From the report, you'll know who you need to include in your communications when you make the switch from StaffHub to Teams.</span></span>

<span data-ttu-id="61dbf-113">Para realizar los pasos de este artículo, debe tener Azure AD Premium.</span><span class="sxs-lookup"><span data-stu-id="61dbf-113">You need to have Azure AD Premium to perform the steps in this article.</span></span>

1. <span data-ttu-id="61dbf-114">Inicie sesión en el portal de Azure.</span><span class="sxs-lookup"><span data-stu-id="61dbf-114">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="61dbf-115">En el panel de la izquierda, haga clic en el recurso **Azure Active Directory** .</span><span class="sxs-lookup"><span data-stu-id="61dbf-115">In the left pane, click the **Azure Active Directory** resource.</span></span>
3. <span data-ttu-id="61dbf-116">En **supervisión**, haga clic en **inicios de sesión**.</span><span class="sxs-lookup"><span data-stu-id="61dbf-116">Under **Monitoring**, click **Sign-ins**.</span></span>
4. <span data-ttu-id="61dbf-117">En **aplicación**, escriba **Microsoft StaffHub**.</span><span class="sxs-lookup"><span data-stu-id="61dbf-117">Under **Application**, type **Microsoft StaffHub**.</span></span>
5. <span data-ttu-id="61dbf-118">Establezca el intervalo de fechas que desee para el informe y, a continuación, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="61dbf-118">Set the date range that you want for the report, and then click **Apply**.</span></span> 

    ![Captura de pantalla que muestra los pasos para mostrar el uso activo de StaffHub](../../media/staffhub-active-usage-report.png)

## <a name="related-topics"></a><span data-ttu-id="61dbf-120">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="61dbf-120">Related topics</span></span>

- [<span data-ttu-id="61dbf-121">Mover los equipos de Microsoft StaffHub a turnos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="61dbf-121">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
