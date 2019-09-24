---
title: Informe de usuarios bloqueados de RTC de Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Obtenga información sobre cómo usar el informe de usuarios bloqueados de RTC en el centro de administración de Microsoft Teams para obtener información general de los usuarios de su organización que no pueden realizar llamadas RTC.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3d7bfff166eec388247b65760c3338cb892984f3
ms.sourcegitcommit: f1c4255b52576c602d528c580941404eb547bc78
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2019
ms.locfileid: "37131680"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a><span data-ttu-id="fb6fa-103">Informe de usuarios bloqueados de RTC de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fb6fa-103">Microsoft Teams PSTN blocked users report</span></span>

<span data-ttu-id="fb6fa-104">El informe de usuarios bloqueados de RTC en el centro de administración de Microsoft Teams le muestra los usuarios de su organización que no pueden realizar llamadas RTC en Teams.</span><span class="sxs-lookup"><span data-stu-id="fb6fa-104">The PSTN blocked users report in the Microsoft Teams admin center shows you the users in your organization who are blocked from making PSTN calls in Teams.</span></span> <span data-ttu-id="fb6fa-105">Puede ver más información sobre los usuarios bloqueados, incluidos su número de teléfono asignado y el motivo por el que fueron bloqueados para realizar llamadas.</span><span class="sxs-lookup"><span data-stu-id="fb6fa-105">You can view more information about each blocked user, including their assigned phone number and the reason they were blocked from making calls.</span></span>

## <a name="view-the-report"></a><span data-ttu-id="fb6fa-106">Ver el informe</span><span class="sxs-lookup"><span data-stu-id="fb6fa-106">View the report</span></span>

<span data-ttu-id="fb6fa-107">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, haga clic en > **informes de uso**de **informes &**.</span><span class="sxs-lookup"><span data-stu-id="fb6fa-107">In the left navigation of the Microsoft Teams admin center, click **Analytics & reports** > **Usage reports**.</span></span> <span data-ttu-id="fb6fa-108">En la pestaña **ver informes** , en **Informe**, seleccione **usuarios bloqueados con RTC**y, a continuación, haga clic en **Ejecutar Informe**.</span><span class="sxs-lookup"><span data-stu-id="fb6fa-108">On the **View reports** tab, under **Report**, select **PSTN blocked users**, and then click **Run report**.</span></span>

<span data-ttu-id="fb6fa-109">![Captura de pantalla del informe de informe usuarios bloqueados de RTC en el centro de administración] (../media/teams-reports-pstn-blocked-users-with-callouts.png "Captura de pantalla del informe de usuarios bloqueados de RTC en el centro de administración de Microsoft Teams con llamadas numeradas")</span><span class="sxs-lookup"><span data-stu-id="fb6fa-109">![Screenshot of the PSTN blocked users report report in the admin center](../media/teams-reports-pstn-blocked-users-with-callouts.png "Screenshot of the PSTN blocked users report in the Microsoft Teams admin center with numbered callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="fb6fa-110">Interpretar el informe</span><span class="sxs-lookup"><span data-stu-id="fb6fa-110">Interpret the report</span></span>

|<span data-ttu-id="fb6fa-111">Globo</span><span class="sxs-lookup"><span data-stu-id="fb6fa-111">Callout</span></span> |<span data-ttu-id="fb6fa-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="fb6fa-112">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="fb6fa-113">**1**</span><span class="sxs-lookup"><span data-stu-id="fb6fa-113">**1**</span></span>   |<span data-ttu-id="fb6fa-114">Cada informe tiene una fecha en la que se generó.</span><span class="sxs-lookup"><span data-stu-id="fb6fa-114">Each report has a date for when it was generated.</span></span> <span data-ttu-id="fb6fa-115">Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad.</span><span class="sxs-lookup"><span data-stu-id="fb6fa-115">The reports usually reflect a 24 to 48 hour latency from time of activity.</span></span> |
|<span data-ttu-id="fb6fa-116">**2**</span><span class="sxs-lookup"><span data-stu-id="fb6fa-116">**2**</span></span>   |<span data-ttu-id="fb6fa-117">El eje X es la fecha.</span><span class="sxs-lookup"><span data-stu-id="fb6fa-117">The X axis is the date.</span></span> <span data-ttu-id="fb6fa-118">El eje Y es el número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="fb6fa-118">The Y axis is the number of users.</span></span> <br><span data-ttu-id="fb6fa-119">Desplace el puntero sobre el punto en una fecha determinada para ver el número de usuarios bloqueados en esa fecha.</span><span class="sxs-lookup"><span data-stu-id="fb6fa-119">Hover over the dot on a given date to see the number of users blocked on that date.</span></span> |
|<span data-ttu-id="fb6fa-120">**3**</span><span class="sxs-lookup"><span data-stu-id="fb6fa-120">**3**</span></span>   |<span data-ttu-id="fb6fa-121">La tabla muestra un desglose de todos los usuarios que están bloqueados para realizar llamadas RTC.</span><span class="sxs-lookup"><span data-stu-id="fb6fa-121">The table gives a breakdown of all users who are blocked from making PSTN calls.</span></span>  <span data-ttu-id="fb6fa-122">Muestra todos los usuarios que tienen asignada una conferencia de audio o de sistema telefónico y le proporcionan más información acerca de cada usuario.</span><span class="sxs-lookup"><span data-stu-id="fb6fa-122">It shows all users who have Phone System or Audio Conferencing assigned and gives you more information about each user.</span></span> <ul><li><span data-ttu-id="fb6fa-123">**Nombre para mostrar** es el nombre para mostrar del usuario.</span><span class="sxs-lookup"><span data-stu-id="fb6fa-123">**Display name** is the display name of the user.</span></span> <span data-ttu-id="fb6fa-124">Puede hacer clic en el nombre para mostrar para ir a la página de configuración del usuario en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fb6fa-124">You can click the display name to go to the user's setting page in the Microsoft Teams admin center.</span></span> </li> <li><span data-ttu-id="fb6fa-125">**Teléfono** es el número que está asignado al usuario.</span><span class="sxs-lookup"><span data-stu-id="fb6fa-125">**Phone** is the number that's assigned to the user.</span></span></li> <li><span data-ttu-id="fb6fa-126">**Motivo de bloqueo** es el motivo por el que el usuario está bloqueado para hacer llamadas.</span><span class="sxs-lookup"><span data-stu-id="fb6fa-126">**Blocked reason** is the reason the user is blocked from making calls.</span></span></li><li><span data-ttu-id="fb6fa-127">La **acción bloqueada** indica si el usuario está bloqueado o desbloqueado para hacer llamadas RTC en Teams.</span><span class="sxs-lookup"><span data-stu-id="fb6fa-127">**Blocked action**  tells you whether the user is blocked or unblocked from making PSTN calls in Teams.</span></span></li> <li><span data-ttu-id="fb6fa-128">**Tiempo bloqueado** es la fecha y hora (UTC) en las que el usuario no pudo realizar llamadas.</span><span class="sxs-lookup"><span data-stu-id="fb6fa-128">**Blocked time** is the date and time (UTC) that the user was blocked from making calls.</span></span></li></li> </ul><span data-ttu-id="fb6fa-129">Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla.</span><span class="sxs-lookup"><span data-stu-id="fb6fa-129">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="fb6fa-130">**4**</span><span class="sxs-lookup"><span data-stu-id="fb6fa-130">**4**</span></span>   |<span data-ttu-id="fb6fa-131">Seleccione **Editar columnas** para agregar o quitar columnas en la tabla.</span><span class="sxs-lookup"><span data-stu-id="fb6fa-131">Select **Edit columns** to add or remove columns in the table.</span></span>|
|<span data-ttu-id="fb6fa-132">**5**</span><span class="sxs-lookup"><span data-stu-id="fb6fa-132">**5**</span></span>   |<span data-ttu-id="fb6fa-133">Seleccione **pantalla completa** para ver el informe en modo de pantalla completa.</span><span class="sxs-lookup"><span data-stu-id="fb6fa-133">Select **Full screen** to view the report in full screen mode.</span></span>|

## <a name="related-topics"></a><span data-ttu-id="fb6fa-134">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="fb6fa-134">Related topics</span></span>

- [<span data-ttu-id="fb6fa-135">Análisis e informes de Teams</span><span class="sxs-lookup"><span data-stu-id="fb6fa-135">Teams analytics and reporting</span></span>](teams-reporting-reference.md)