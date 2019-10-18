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
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 49091f7d8ada565adea61bf8219c6da828358893
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569668"
---
# <a name="run-a-report-to-show-active-staffhub-usage"></a><span data-ttu-id="acb0c-103">Ejecutar un informe para mostrar el uso de StaffHub activo</span><span class="sxs-lookup"><span data-stu-id="acb0c-103">Run a report to show active StaffHub usage</span></span>

> [!IMPORTANT]
> <span data-ttu-id="acb0c-104">A partir del 31 de diciembre de 2019, Microsoft StaffHub se retirará.</span><span class="sxs-lookup"><span data-stu-id="acb0c-104">Effective December 31, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="acb0c-105">Estamos construyendo las capacidades de StaffHub en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="acb0c-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="acb0c-106">En la actualidad, Teams incluye la aplicación de turnos para la administración de la programación, y las funciones adicionales se aplicarán a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="acb0c-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="acb0c-107">StaffHub dejará de funcionar para todos los usuarios el 31 de diciembre de 2019.</span><span class="sxs-lookup"><span data-stu-id="acb0c-107">StaffHub will stop working for all users on December 31, 2019.</span></span> <span data-ttu-id="acb0c-108">Cualquier persona que intente abrir StaffHub recibirá un mensaje para que pueda descargar Teams.</span><span class="sxs-lookup"><span data-stu-id="acb0c-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="acb0c-109">Para obtener más información, consulte [Microsoft StaffHub para que se retirará](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="acb0c-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="acb0c-110">Siga los pasos descritos en este artículo para ejecutar un informe para obtener una lista de los usuarios activos de StaffHub de su organización.</span><span class="sxs-lookup"><span data-stu-id="acb0c-110">Use the steps in this article to run a report to get a list of active StaffHub users in your organization.</span></span> <span data-ttu-id="acb0c-111">Esta información puede resultar útil cuando se prepara para [mover los equipos de StaffHub a Microsoft Teams](move-staffhub-teams-to-shifts-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="acb0c-111">This information may come in handy when you prepare to [move your StaffHub teams to Microsoft Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span> <span data-ttu-id="acb0c-112">En el informe, sabrá quién tiene que incluir en las comunicaciones al cambiar de StaffHub a teams.</span><span class="sxs-lookup"><span data-stu-id="acb0c-112">From the report, you'll know who you need to include in your communications when you make the switch from StaffHub to Teams.</span></span>

<span data-ttu-id="acb0c-113">Para realizar los pasos de este artículo, debe tener Azure AD Premium.</span><span class="sxs-lookup"><span data-stu-id="acb0c-113">You need to have Azure AD Premium to perform the steps in this article.</span></span>

1. <span data-ttu-id="acb0c-114">Inicie sesión en el portal de Azure.</span><span class="sxs-lookup"><span data-stu-id="acb0c-114">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="acb0c-115">En el panel de la izquierda, haga clic en el recurso **Azure Active Directory** .</span><span class="sxs-lookup"><span data-stu-id="acb0c-115">In the left pane, click the **Azure Active Directory** resource.</span></span>
3. <span data-ttu-id="acb0c-116">En **supervisión**, haga clic en **inicios de sesión**.</span><span class="sxs-lookup"><span data-stu-id="acb0c-116">Under **Monitoring**, click **Sign-ins**.</span></span>
4. <span data-ttu-id="acb0c-117">En **aplicación**, escriba **Microsoft StaffHub**.</span><span class="sxs-lookup"><span data-stu-id="acb0c-117">Under **Application**, type **Microsoft StaffHub**.</span></span>
5. <span data-ttu-id="acb0c-118">Establezca el intervalo de fechas que desee para el informe y, a continuación, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="acb0c-118">Set the date range that you want for the report, and then click **Apply**.</span></span> 

    ![Captura de pantalla que muestra los pasos para mostrar el uso activo de StaffHub](../../media/staffhub-active-usage-report.png)

## <a name="related-topics"></a><span data-ttu-id="acb0c-120">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="acb0c-120">Related topics</span></span>

- [<span data-ttu-id="acb0c-121">Mover los equipos de Microsoft StaffHub a turnos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="acb0c-121">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
