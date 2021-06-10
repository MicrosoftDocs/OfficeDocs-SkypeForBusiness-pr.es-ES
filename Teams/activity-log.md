---
title: Ver las asignaciones de directivas en el registro de actividades en el centro Microsoft Teams administración
author: cichur
ms.author: v-cichur
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Obtenga información sobre cómo ver las actividades de asignación de directivas en el registro de actividades en el Microsoft Teams de administración.
localization_priority: Normal
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a8d1d49d187808b768b4a92c64c4e667ca0ea8f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821320"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a><span data-ttu-id="d78b8-103">Ver las asignaciones de directivas en el registro de actividades</span><span class="sxs-lookup"><span data-stu-id="d78b8-103">View your policy assignments in the Activity log</span></span>

<span data-ttu-id="d78b8-104">Al asignar directivas a usuarios en el centro de administración de Microsoft Teams, puede ver el estado de esas asignaciones de directivas en el registro de actividades.</span><span class="sxs-lookup"><span data-stu-id="d78b8-104">When you assign policies to users in the Microsoft Teams admin center, you can view the status of those policy assignments in the Activity log.</span></span> <span data-ttu-id="d78b8-105">El registro de actividades muestra las asignaciones de directivas a lotes de más de 20 usuarios a través del centro de administración de Microsoft Teams desde los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="d78b8-105">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="d78b8-106">Tenga en cuenta que el registro de actividades no muestra asignaciones de paquetes de directiva, asignaciones de directivas a lotes de menos de 20 usuarios a través del centro de administración de Microsoft Teams o asignaciones de directivas a través de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d78b8-106">Keep in mind that the Activity log doesn't show policy package assignments, policy assignments to batches of less than 20 users through the Microsoft Teams admin center, or policy assignments through PowerShell.</span></span>

![Captura de pantalla de la página Registro de actividades](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a><span data-ttu-id="d78b8-108">Ver las actividades de asignación de directivas en el registro de actividades</span><span class="sxs-lookup"><span data-stu-id="d78b8-108">View your policy assignment activities in the Activity log</span></span>

<span data-ttu-id="d78b8-109">Para ver las asignaciones de directivas en el registro de actividades:</span><span class="sxs-lookup"><span data-stu-id="d78b8-109">To view your policy assignments in the Activity log:</span></span>

1. <span data-ttu-id="d78b8-110">En el panel de navegación izquierdo del Microsoft Teams de administración, vaya a Panel y, a continuación, en Registro de actividades, seleccione Ver **detalles.**</span><span class="sxs-lookup"><span data-stu-id="d78b8-110">In the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity Log**, select **View details**.</span></span>
2. <span data-ttu-id="d78b8-111">Puede ver todas las asignaciones de directivas o filtrar la lista por estado para mostrar solo las tareas no iniciadas, en curso **o** **completadas.**</span><span class="sxs-lookup"><span data-stu-id="d78b8-111">You can view all policy assignments or filter the list by status to show only assignments that are **Not started**, **In progress**, or **Completed**.</span></span> <span data-ttu-id="d78b8-112">Verá la siguiente información sobre cada tarea:</span><span class="sxs-lookup"><span data-stu-id="d78b8-112">You'll see the following information about each assignment:</span></span>
    - <span data-ttu-id="d78b8-113">**Nombre:** el nombre de la asignación de directivas.</span><span class="sxs-lookup"><span data-stu-id="d78b8-113">**Name**: The name of the policy assignment.</span></span> <span data-ttu-id="d78b8-114">Haga clic en el vínculo para ver más detalles.</span><span class="sxs-lookup"><span data-stu-id="d78b8-114">Click the link to view more details.</span></span> <span data-ttu-id="d78b8-115">Esto incluye el número de usuarios a los que se asignó la directiva y el número de tareas completadas, en curso y no iniciadas.</span><span class="sxs-lookup"><span data-stu-id="d78b8-115">This includes the number of users the policy was assigned to and the number of assignments completed, in progress, and not started.</span></span> <span data-ttu-id="d78b8-116">También verá la lista de usuarios en el lote, así como el estado y el resultado de cada usuario.</span><span class="sxs-lookup"><span data-stu-id="d78b8-116">You'll also see the list of users in the batch, and the status and result for each user.</span></span> <span data-ttu-id="d78b8-117">Aquí se muestra un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d78b8-117">Here's an example:</span></span>

        ![Captura de pantalla de la](media/activity-log-policy-assignment-detail.png)

    - <span data-ttu-id="d78b8-119">**Enviado:** Fecha y hora en que se envió la asignación de directiva.</span><span class="sxs-lookup"><span data-stu-id="d78b8-119">**Submitted**: Date and time the policy assignment was submitted.</span></span>
    - <span data-ttu-id="d78b8-120">**Hora de finalización:** fecha y hora en que se completó la asignación de directivas.</span><span class="sxs-lookup"><span data-stu-id="d78b8-120">**Completion time**: Date and time the policy assignment was completed.</span></span>
    - <span data-ttu-id="d78b8-121">**Impacto en:** Número de usuarios en el lote.</span><span class="sxs-lookup"><span data-stu-id="d78b8-121">**Impact on**: Number of users in the batch.</span></span>
    - <span data-ttu-id="d78b8-122">**Estado general:** Estado de la asignación de directivas.</span><span class="sxs-lookup"><span data-stu-id="d78b8-122">**Overall status**: Status of the policy assignment.</span></span>

> [!NOTE]
> <span data-ttu-id="d78b8-123">También puede acceder al registro de actividades desde la **página** Usuarios.</span><span class="sxs-lookup"><span data-stu-id="d78b8-123">You can also get to the Activity log from the **Users** page.</span></span> <span data-ttu-id="d78b8-124">Después de hacer **clic en Aplicar** para enviar una asignación de directiva en masa, verá un banner en la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="d78b8-124">After you click **Apply** to submit a bulk policy assignment, you'll see a banner at the top of the page.</span></span> <span data-ttu-id="d78b8-125">Haga clic en **el vínculo Registro** de actividades en el banner.</span><span class="sxs-lookup"><span data-stu-id="d78b8-125">Click the **Activity log** link in the banner.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d78b8-126">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d78b8-126">Related topics</span></span>

- [<span data-ttu-id="d78b8-127">Asignar directivas a los usuarios</span><span class="sxs-lookup"><span data-stu-id="d78b8-127">Assign policies to users</span></span>](assign-policies.md)
