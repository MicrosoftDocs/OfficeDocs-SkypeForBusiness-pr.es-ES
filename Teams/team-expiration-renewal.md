---
title: Caducidad y renovación de equipos en Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Obtenga información sobre la caducidad y la renovación del equipo y sobre cómo usar Microsoft 365 o la Directiva de expiración de grupos de Microsoft 365 para limpiar automáticamente los equipos no usados en Microsoft Teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 34984c545e3e6593c9d5168a81d3465ce391dab2
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638559"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a><span data-ttu-id="4a455-103">Caducidad y renovación de equipos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4a455-103">Team expiration and renewal in Microsoft Teams</span></span>

<span data-ttu-id="4a455-104">Las organizaciones con una gran cantidad de equipos suelen tener equipos que nunca se usan realmente.</span><span class="sxs-lookup"><span data-stu-id="4a455-104">Organizations with a large number of teams often have teams that are never actually used.</span></span> <span data-ttu-id="4a455-105">Esto puede suceder por varias razones, entre las que se incluyen la experimentación de productos, la colaboración de equipos a corto plazo o los propietarios de equipos que salen de la organización.</span><span class="sxs-lookup"><span data-stu-id="4a455-105">This can happen because of several reasons including product experimentation, short-term team collaboration, or team owners leaving the organization.</span></span> <span data-ttu-id="4a455-106">Con el tiempo, esos equipos pueden acumular y crear una carga para los recursos de inquilino.</span><span class="sxs-lookup"><span data-stu-id="4a455-106">Over time, such teams can accumulate and create a burden on tenant resources.</span></span>  

<span data-ttu-id="4a455-107">Para frenar el número de equipos sin usar, como administrador, puede usar [microsoft 365 o la Directiva de expiración de grupo de microsoft 365](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups-expiration-policy) para limpiar automáticamente los equipos que no se usan.</span><span class="sxs-lookup"><span data-stu-id="4a455-107">To curb the number of unused teams, as an admin, you can use [Microsoft 365 or Microsoft 365 group expiration policy](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups-expiration-policy) to automatically clean up unused teams.</span></span> <span data-ttu-id="4a455-108">Debido a que los equipos están respaldados por grupos, las directivas de expiración de grupos también se aplican automáticamente a los equipos.</span><span class="sxs-lookup"><span data-stu-id="4a455-108">Because teams are backed by groups, group expiration policies automatically apply to teams as well.</span></span>

<span data-ttu-id="4a455-109">Al aplicar una directiva de expiración a un equipo, el propietario de un equipo recibe una notificación para la renovación de equipo 30 días, 15 días y 1 día antes de la fecha de expiración del equipo.</span><span class="sxs-lookup"><span data-stu-id="4a455-109">When you apply an expiration policy to a team, a team owner receives a notification for team renewal 30 days, 15 days and 1 day before the team's expiration date.</span></span> <span data-ttu-id="4a455-110">Cuando el propietario del equipo recibe la notificación, puede hacer clic en **renovar ahora** en configuración del equipo para renovar el equipo.</span><span class="sxs-lookup"><span data-stu-id="4a455-110">When the team owner receives the notification, they can click **Renew now** in team settings to renew the team.</span></span>

<span data-ttu-id="4a455-111">![Captura de pantalla del botón renovar ahora para renovar un equipo en la configuración del equipo](media/team-expiration.png "Captura de pantalla del botón renovar ahora para renovar un equipo en la configuración del equipo")</span><span class="sxs-lookup"><span data-stu-id="4a455-111">![Screenshot of the Renew Now button to renew a team in team settings](media/team-expiration.png "Screenshot of the Renew Now button to renew a team in team settings")</span></span>

<span data-ttu-id="4a455-112">Si el propietario del equipo no renueva el equipo, el equipo se coloca en un estado "eliminado temporalmente", lo que significa que se puede restaurar en los próximos 30 días.</span><span class="sxs-lookup"><span data-stu-id="4a455-112">If the team owner doesn't renew the team, the team is put in a "soft-deleted" state, which means it can be restored within the next 30 days.</span></span>

## <a name="team-auto-renewal"></a><span data-ttu-id="4a455-113">Renovación automática de equipo</span><span class="sxs-lookup"><span data-stu-id="4a455-113">Team auto-renewal</span></span>

<span data-ttu-id="4a455-114">Puede haber ocasiones en las que el propietario de un equipo no pueda renovar el equipo, tal vez porque se hayan olvidado de renovar o se hayan ausentado cuando venza la renovación.</span><span class="sxs-lookup"><span data-stu-id="4a455-114">There can be times when a team owner is unable to renew the team perhaps because they forgot to renew or were away when renewal was due.</span></span> <span data-ttu-id="4a455-115">En estos escenarios, un equipo en uso activo puede ser eliminado a causa de las directivas de expiración que se aplican al equipo.</span><span class="sxs-lookup"><span data-stu-id="4a455-115">In these scenarios, a team in active use can get deleted because of expiration policies that apply to the team.</span></span>  

<span data-ttu-id="4a455-116">Para evitar la eliminación accidental, la renovación automática se habilita automáticamente para un equipo en la Directiva de expiración del grupo.</span><span class="sxs-lookup"><span data-stu-id="4a455-116">To prevent accidental deletion, auto-renewal is automatically enabled for a team in the group expiration policy.</span></span> <span data-ttu-id="4a455-117">Cuando la Directiva de expiración del grupo está configurada, cualquier equipo que tenga al menos una visita de canal desde cualquier miembro del equipo antes de la fecha de expiración se renueva automáticamente sin intervención manual del propietario del equipo.</span><span class="sxs-lookup"><span data-stu-id="4a455-117">When the group expiration policy is set up, any team that has at least one channel visit from any team member before its expiration date is automatically renewed without any manual intervention from the team owner.</span></span>

## <a name="known-issues"></a><span data-ttu-id="4a455-118">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="4a455-118">Known issues</span></span>

<span data-ttu-id="4a455-119">**La fecha de expiración del equipo y el grupo subyacente no coinciden**</span><span class="sxs-lookup"><span data-stu-id="4a455-119">**Expiration date of team and underlying group don't match**</span></span>

<span data-ttu-id="4a455-120">Antes de renovar un equipo, primero se renueva el grupo que respalda al equipo.</span><span class="sxs-lookup"><span data-stu-id="4a455-120">Before a team is renewed, the group that backs the team is renewed first.</span></span> <span data-ttu-id="4a455-121">Como parte de la renovación, se establece una nueva fecha de caducidad en el grupo para una fecha futura.</span><span class="sxs-lookup"><span data-stu-id="4a455-121">As part of renewal, a new expiry date is set on the group for a future date.</span></span> <span data-ttu-id="4a455-122">Es posible que esta nueva fecha no esté visible de forma inmediata en Teams.</span><span class="sxs-lookup"><span data-stu-id="4a455-122">This new date may not be immediately visible in Teams.</span></span> <span data-ttu-id="4a455-123">La sincronización puede demorar hasta 24 horas. Si ve una discrepancia entre la fecha de caducidad de un equipo y su grupo subyacente, espere 24 horas antes de buscar asistencia.</span><span class="sxs-lookup"><span data-stu-id="4a455-123">It can take up to 24 hours to sync. If you see a discrepancy between the expiry date for a team and its underlying group, wait 24 hours before seeking further support.</span></span>
