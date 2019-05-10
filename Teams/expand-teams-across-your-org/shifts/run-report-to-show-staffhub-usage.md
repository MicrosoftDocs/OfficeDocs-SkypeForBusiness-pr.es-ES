---
title: Ejecutar un informe para mostrar el uso de StaffHub activo
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 05/10/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo ejecutar un informe para obtener una lista de usuarios activos de StaffHub en su organización.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e66e889fbc7fb26b8fda55beb889bc95b155666d
ms.sourcegitcommit: b2acf18ba6487154ebb4ee46938e96dc56cb2c9a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/09/2019
ms.locfileid: "33868203"
---
# <a name="run-a-report-to-show-active-staffhub-usage"></a><span data-ttu-id="cb733-103">Ejecutar un informe para mostrar el uso de StaffHub activo</span><span class="sxs-lookup"><span data-stu-id="cb733-103">Run a report to show active StaffHub usage</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cb733-104">Eficaces se deben retirarse el 1 de octubre de 2019, Microsoft StaffHub.</span><span class="sxs-lookup"><span data-stu-id="cb733-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="cb733-105">Capacidades de StaffHub que estamos creando en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cb733-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="cb733-106">En la actualidad, los equipos incluye la aplicación de turnos para la administración de programación y funciones adicionales se lleve a cabo a través del tiempo.</span><span class="sxs-lookup"><span data-stu-id="cb733-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="cb733-107">StaffHub dejará de funcionar para todos los usuarios en el 1 de octubre de 2019.</span><span class="sxs-lookup"><span data-stu-id="cb733-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="cb733-108">Cualquier persona que intenta abrir StaffHub se mostrará un mensaje que les dirige a descargar los equipos.</span><span class="sxs-lookup"><span data-stu-id="cb733-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="cb733-109">Para obtener más información, vea [Microsoft StaffHub retirarse](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="cb733-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="cb733-110">Use los pasos de este artículo para ejecutar un informe para obtener una lista de usuarios activos de StaffHub en su organización.</span><span class="sxs-lookup"><span data-stu-id="cb733-110">Use the steps in this article to run a report to get a list of active StaffHub users in your organization.</span></span> <span data-ttu-id="cb733-111">Esta información puede resultar útil cuando se prepare para [mover los equipos StaffHub de equipos de Microsoft](move-staffhub-teams-to-shifts-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="cb733-111">This information may come in handy when you prepare to [move your StaffHub teams to Microsoft Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span> <span data-ttu-id="cb733-112">Desde el informe, sabrá que necesitan incluir en las comunicaciones al realizar el cambio desde StaffHub a los equipos.</span><span class="sxs-lookup"><span data-stu-id="cb733-112">From the report, you'll know who you need to include in your communications when you make the switch from StaffHub to Teams.</span></span>

<span data-ttu-id="cb733-113">Necesita tener Azure AD Premium para llevar a cabo los pasos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="cb733-113">You need to have Azure AD Premium to perform the steps in this article.</span></span>

1. <span data-ttu-id="cb733-114">Inicie sesión en el portal de Azure.</span><span class="sxs-lookup"><span data-stu-id="cb733-114">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="cb733-115">En el panel izquierdo, haga clic en el recurso de **Azure Active Directory** .</span><span class="sxs-lookup"><span data-stu-id="cb733-115">In the left pane, click the **Azure Active Directory** resource.</span></span>
3. <span data-ttu-id="cb733-116">Debajo de **supervisión**, haga clic en **inicios de sesión**.</span><span class="sxs-lookup"><span data-stu-id="cb733-116">Under **Monitoring**, click **Sign-ins**.</span></span>
4. <span data-ttu-id="cb733-117">En la **aplicación**, escriba **StaffHub de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="cb733-117">Under **Application**, type **Microsoft StaffHub**.</span></span>
5. <span data-ttu-id="cb733-118">Establecer el intervalo de fechas que desee para el informe y, a continuación, haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="cb733-118">Set the date range that you want for the report, and then click **Apply**.</span></span> 

    ![Captura de pantalla que muestra los pasos para ejecutar el informe para mostrar el uso de StaffHub activo en el portal de Azure](../../media/staffhub-active-usage-report.png)

## <a name="related-topics"></a><span data-ttu-id="cb733-120">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="cb733-120">Related topics</span></span>

- [<span data-ttu-id="cb733-121">Mover los equipos de Microsoft StaffHub a turnos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cb733-121">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
