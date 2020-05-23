---
title: Ver las asignaciones de directivas en el registro de actividades del centro de administración de Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Obtenga información sobre cómo ver las actividades de asignación de directivas en el registro de actividades en el centro de administración de Microsoft Teams.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7a363d934ffd66d04bc3eb778380613e33e460a9
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350096"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a><span data-ttu-id="e3da9-103">Ver las asignaciones de directivas en el registro de actividades</span><span class="sxs-lookup"><span data-stu-id="e3da9-103">View your policy assignments in the Activity log</span></span>

<span data-ttu-id="e3da9-104">Al asignar directivas a usuarios en el centro de administración de Microsoft Teams, puede ver el estado de esas asignaciones de directiva en el registro de actividades.</span><span class="sxs-lookup"><span data-stu-id="e3da9-104">When you assign policies to users in the Microsoft Teams admin center, you can view the status of those policy assignments in the Activity log.</span></span> <span data-ttu-id="e3da9-105">En el registro de actividades se muestran asignaciones de directivas de los lotes de más de 20 usuarios a través del centro de administración de Microsoft Teams desde los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="e3da9-105">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="e3da9-106">Tenga en cuenta que el registro de actividades no muestra asignaciones de paquetes de directivas, asignaciones de directiva a lotes de menos de 20 usuarios a través del centro de administración de Microsoft Teams o asignación de directivas a través de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e3da9-106">Keep in mind that the Activity log doesn't show policy package assignments, policy assignments to batches of less than 20 users through the Microsoft Teams admin center, or policy assignments through PowerShell.</span></span>

![Captura de pantalla de la página Registro de actividades](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a><span data-ttu-id="e3da9-108">Ver las actividades de asignación de directivas en el registro de actividades</span><span class="sxs-lookup"><span data-stu-id="e3da9-108">View your policy assignment activities in the Activity log</span></span>

<span data-ttu-id="e3da9-109">Para ver las asignaciones de directivas en el registro de actividades:</span><span class="sxs-lookup"><span data-stu-id="e3da9-109">To view your policy assignments in the Activity log:</span></span>

1. <span data-ttu-id="e3da9-110">En el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Panel**y, a continuación, en **registro de actividades**, seleccione **Ver detalles**.</span><span class="sxs-lookup"><span data-stu-id="e3da9-110">In the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity Log**, select **View details**.</span></span>
2. <span data-ttu-id="e3da9-111">Puede ver todas las asignaciones de directivas o filtrar la lista por estado para que solo se muestren las asignaciones que **no estén iniciadas**, estén **en curso**o **completadas**.</span><span class="sxs-lookup"><span data-stu-id="e3da9-111">You can view all policy assignments or filter the list by status to show only assignments that are **Not started**, **In progress**, or **Completed**.</span></span> <span data-ttu-id="e3da9-112">Verá la siguiente información sobre cada asignación:</span><span class="sxs-lookup"><span data-stu-id="e3da9-112">You'll see the following information about each assignment:</span></span>
    - <span data-ttu-id="e3da9-113">**Nombre**: el nombre de la asignación de directiva.</span><span class="sxs-lookup"><span data-stu-id="e3da9-113">**Name**: The name of the policy assignment.</span></span> <span data-ttu-id="e3da9-114">Haga clic en el vínculo para ver más detalles.</span><span class="sxs-lookup"><span data-stu-id="e3da9-114">Click the link to view more details.</span></span> <span data-ttu-id="e3da9-115">Esto incluye el número de usuarios a los que se asignó la Directiva y el número de tareas completadas, en curso y no iniciadas.</span><span class="sxs-lookup"><span data-stu-id="e3da9-115">This includes the number of users the policy was assigned to and the number of assignments completed, in progress, and not started.</span></span> <span data-ttu-id="e3da9-116">También verá la lista de usuarios en el lote, así como el estado y el resultado de cada usuario.</span><span class="sxs-lookup"><span data-stu-id="e3da9-116">You'll also see the list of users in the batch, and the status and result for each user.</span></span> <span data-ttu-id="e3da9-117">Aquí se muestra un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e3da9-117">Here's an example:</span></span>

        ![Captura de pantalla de la](media/activity-log-policy-assignment-detail.png)

    - <span data-ttu-id="e3da9-119">**Enviado**: fecha y hora en que se envió la asignación de directiva.</span><span class="sxs-lookup"><span data-stu-id="e3da9-119">**Submitted**: Date and time the policy assignment was submitted.</span></span>
    - <span data-ttu-id="e3da9-120">**Hora de finalización**: fecha y hora en que se completó la asignación de directiva.</span><span class="sxs-lookup"><span data-stu-id="e3da9-120">**Completion time**: Date and time the policy assignment was completed.</span></span>
    - <span data-ttu-id="e3da9-121">**Impacto en**: número de usuarios en el lote.</span><span class="sxs-lookup"><span data-stu-id="e3da9-121">**Impact on**: Number of users in the batch.</span></span>
    - <span data-ttu-id="e3da9-122">**Estado general**: estado de la asignación de directiva.</span><span class="sxs-lookup"><span data-stu-id="e3da9-122">**Overall status**: Status of the policy assignment.</span></span>

> [!NOTE]
> <span data-ttu-id="e3da9-123">También puede acceder al registro de actividades desde la página **usuarios** .</span><span class="sxs-lookup"><span data-stu-id="e3da9-123">You can also get to the Activity log from the **Users** page.</span></span> <span data-ttu-id="e3da9-124">Después de hacer clic en **aplicar** para enviar una asignación de directiva masiva, verá una pancarta en la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="e3da9-124">After you click **Apply** to submit a bulk policy assignment, you'll see a banner at the top of the page.</span></span> <span data-ttu-id="e3da9-125">Haga clic en el vínculo **registro de actividades** de la pancarta.</span><span class="sxs-lookup"><span data-stu-id="e3da9-125">Click the **Activity log** link in the banner.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e3da9-126">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="e3da9-126">Related topics</span></span>

- [<span data-ttu-id="e3da9-127">Asignar directivas a usuarios</span><span class="sxs-lookup"><span data-stu-id="e3da9-127">Assign policies to users</span></span>](assign-policies.md)
