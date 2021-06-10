---
title: Microsoft Teams Informe de usuarios bloqueados rtc
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
MS.collection:
- M365-voice
description: Use el informe usuarios bloqueados RTC en el centro de administración de Microsoft Teams para obtener información general sobre los usuarios de Teams de su organización que están bloqueados para realizar llamadas RTC.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ed775c3796e40a775b3be2b78f22e162a047bf78
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809340"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a><span data-ttu-id="67b77-103">Microsoft Teams Informe de usuarios bloqueados rtc</span><span class="sxs-lookup"><span data-stu-id="67b77-103">Microsoft Teams PSTN blocked users report</span></span>

<span data-ttu-id="67b77-104">El informe usuarios bloqueados rtc en el centro de administración de Microsoft Teams muestra los usuarios de su organización que están bloqueados para realizar llamadas RTC en Teams.</span><span class="sxs-lookup"><span data-stu-id="67b77-104">The PSTN blocked users report in the Microsoft Teams admin center shows you the users in your organization who are blocked from making PSTN calls in Teams.</span></span> <span data-ttu-id="67b77-105">Puede ver más información sobre cada usuario bloqueado, incluido su número de teléfono asignado y la razón por la que se les bloqueó realizar llamadas.</span><span class="sxs-lookup"><span data-stu-id="67b77-105">You can view more information about each blocked user, including their assigned phone number and the reason they were blocked from making calls.</span></span>

## <a name="view-the-pstn-blocked-users-report"></a><span data-ttu-id="67b77-106">Ver el informe de usuarios bloqueados de RTC</span><span class="sxs-lookup"><span data-stu-id="67b77-106">View the PSTN blocked users report</span></span>

<span data-ttu-id="67b77-107">En el panel de navegación izquierdo del centro Microsoft Teams administración, haga clic **en Análisis & informes de**  >  **uso.**</span><span class="sxs-lookup"><span data-stu-id="67b77-107">In the left navigation of the Microsoft Teams admin center, click **Analytics & reports** > **Usage reports**.</span></span> <span data-ttu-id="67b77-108">En la pestaña **Ver informes,** **en** Informe, seleccione Usuarios bloqueados por **RTC** y, a continuación, haga clic en **Ejecutar informe.**</span><span class="sxs-lookup"><span data-stu-id="67b77-108">On the **View reports** tab, under **Report**, select **PSTN blocked users**, and then click **Run report**.</span></span>

<span data-ttu-id="67b77-109">![Captura de pantalla del informe de usuarios bloqueados rtc en el centro de administración](../media/teams-reports-pstn-blocked-users-with-callouts.png "Captura de pantalla del informe de usuarios bloqueados rtc en el Microsoft Teams de administración con llamadas numeradas")</span><span class="sxs-lookup"><span data-stu-id="67b77-109">![Screenshot of the PSTN blocked users report report in the admin center](../media/teams-reports-pstn-blocked-users-with-callouts.png "Screenshot of the PSTN blocked users report in the Microsoft Teams admin center with numbered callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="67b77-110">Interpretar el informe</span><span class="sxs-lookup"><span data-stu-id="67b77-110">Interpret the report</span></span>

|<span data-ttu-id="67b77-111">Globo</span><span class="sxs-lookup"><span data-stu-id="67b77-111">Callout</span></span> |<span data-ttu-id="67b77-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="67b77-112">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="67b77-113">**1**</span><span class="sxs-lookup"><span data-stu-id="67b77-113">**1**</span></span>   |<span data-ttu-id="67b77-114">Cada informe tiene una fecha para cuándo se generó.</span><span class="sxs-lookup"><span data-stu-id="67b77-114">Each report has a date for when it was generated.</span></span> <span data-ttu-id="67b77-115">Normalmente, el informe refleja una latencia de 24 a 48 horas desde el momento de actividad.</span><span class="sxs-lookup"><span data-stu-id="67b77-115">The reports usually reflect a 24 to 48 hour latency from time of activity.</span></span> |
|<span data-ttu-id="67b77-116">**2**</span><span class="sxs-lookup"><span data-stu-id="67b77-116">**2**</span></span>   |<span data-ttu-id="67b77-117">El eje X es la fecha.</span><span class="sxs-lookup"><span data-stu-id="67b77-117">The X axis is the date.</span></span> <span data-ttu-id="67b77-118">El eje Y es el número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="67b77-118">The Y axis is the number of users.</span></span> <br><span data-ttu-id="67b77-119">Mantenga el puntero sobre el punto en una fecha determinada para ver el número de usuarios bloqueados en esa fecha.</span><span class="sxs-lookup"><span data-stu-id="67b77-119">Hover over the dot on a given date to see the number of users blocked on that date.</span></span> |
|<span data-ttu-id="67b77-120">**3**</span><span class="sxs-lookup"><span data-stu-id="67b77-120">**3**</span></span>   |<span data-ttu-id="67b77-121">La tabla proporciona un desglose de todos los usuarios que están bloqueados para realizar llamadas RTC.</span><span class="sxs-lookup"><span data-stu-id="67b77-121">The table gives a breakdown of all users who are blocked from making PSTN calls.</span></span>  <span data-ttu-id="67b77-122">Muestra todos los usuarios que tienen Sistema telefónico o Audioconferencia asignadas y le proporciona más información sobre cada usuario.</span><span class="sxs-lookup"><span data-stu-id="67b77-122">It shows all users who have Phone System or Audio Conferencing assigned and gives you more information about each user.</span></span> <ul><li><span data-ttu-id="67b77-123">**Nombre para mostrar** es el nombre para mostrar del usuario.</span><span class="sxs-lookup"><span data-stu-id="67b77-123">**Display name** is the display name of the user.</span></span> <span data-ttu-id="67b77-124">Puede hacer clic en el nombre para mostrar para ir a la página de configuración del usuario en el Microsoft Teams de administración.</span><span class="sxs-lookup"><span data-stu-id="67b77-124">You can click the display name to go to the user's setting page in the Microsoft Teams admin center.</span></span> </li> <li><span data-ttu-id="67b77-125">**Teléfono** es el número asignado al usuario.</span><span class="sxs-lookup"><span data-stu-id="67b77-125">**Phone** is the number that's assigned to the user.</span></span></li> <li><span data-ttu-id="67b77-126">**El motivo bloqueado** es la razón por la que el usuario está bloqueado para realizar llamadas.</span><span class="sxs-lookup"><span data-stu-id="67b77-126">**Blocked reason** is the reason the user is blocked from making calls.</span></span></li><li><span data-ttu-id="67b77-127">**La acción bloqueada** le indica si el usuario está bloqueado o desbloqueado para realizar llamadas RTC en Teams.</span><span class="sxs-lookup"><span data-stu-id="67b77-127">**Blocked action**  tells you whether the user is blocked or unblocked from making PSTN calls in Teams.</span></span></li> <li><span data-ttu-id="67b77-128">**Hora bloqueada** es la fecha y hora (UTC) en las que el usuario no ha hecho llamadas.</span><span class="sxs-lookup"><span data-stu-id="67b77-128">**Blocked time** is the date and time (UTC) that the user was blocked from making calls.</span></span></li></li> </ul><span data-ttu-id="67b77-129">Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla.</span><span class="sxs-lookup"><span data-stu-id="67b77-129">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="67b77-130">**4**</span><span class="sxs-lookup"><span data-stu-id="67b77-130">**4**</span></span>   |<span data-ttu-id="67b77-131">Seleccione **Editar columnas** para agregar o quitar columnas en la tabla.</span><span class="sxs-lookup"><span data-stu-id="67b77-131">Select **Edit columns** to add or remove columns in the table.</span></span>|
|<span data-ttu-id="67b77-132">**5**</span><span class="sxs-lookup"><span data-stu-id="67b77-132">**5**</span></span>   |<span data-ttu-id="67b77-133">Seleccione **Pantalla completa** para ver el informe en modo de pantalla completa.</span><span class="sxs-lookup"><span data-stu-id="67b77-133">Select **Full screen** to view the report in full screen mode.</span></span>|

## <a name="related-topics"></a><span data-ttu-id="67b77-134">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="67b77-134">Related topics</span></span>

- [<span data-ttu-id="67b77-135">Análisis e informes de Teams</span><span class="sxs-lookup"><span data-stu-id="67b77-135">Teams analytics and reporting</span></span>](teams-reporting-reference.md)