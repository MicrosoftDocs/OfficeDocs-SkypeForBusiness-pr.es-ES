---
title: Expiración y renovación del equipo en Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Obtenga información sobre la expiración y renovación del equipo y cómo usar Microsoft 365 directiva de expiración de grupo para limpiar automáticamente los equipos sin usar en Microsoft Teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 606d957b703725d631beec38237f4d9b4272433e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116958"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a><span data-ttu-id="56c31-103">Expiración y renovación del equipo en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="56c31-103">Team expiration and renewal in Microsoft Teams</span></span>

<span data-ttu-id="56c31-104">Las organizaciones con un gran número de equipos a menudo tienen equipos que nunca se usan realmente.</span><span class="sxs-lookup"><span data-stu-id="56c31-104">Organizations with a large number of teams often have teams that are never actually used.</span></span> <span data-ttu-id="56c31-105">Esto puede ocurrir debido a varios motivos, como la experimentación de productos, la colaboración de equipo a corto plazo o la salida de los propietarios de equipos de la organización.</span><span class="sxs-lookup"><span data-stu-id="56c31-105">This can happen because of several reasons including product experimentation, short-term team collaboration, or team owners leaving the organization.</span></span> <span data-ttu-id="56c31-106">Con el tiempo, estos equipos pueden acumular y crear una carga para los recursos del inquilino.</span><span class="sxs-lookup"><span data-stu-id="56c31-106">Over time, such teams can accumulate and create a burden on tenant resources.</span></span>  

<span data-ttu-id="56c31-107">Para reducir el número de equipos sin usar, [](/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) como administrador, puede usar la directiva de expiración de Microsoft 365 grupo para limpiar automáticamente los equipos sin usar.</span><span class="sxs-lookup"><span data-stu-id="56c31-107">To curb the number of unused teams, as an admin, you can use [Microsoft 365 group expiration policy](/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) to automatically clean up unused teams.</span></span> <span data-ttu-id="56c31-108">Dado que los grupos tienen una copia de seguridad de los equipos, las directivas de expiración del grupo también se aplican automáticamente a los equipos.</span><span class="sxs-lookup"><span data-stu-id="56c31-108">Because teams are backed by groups, group expiration policies automatically apply to teams as well.</span></span>

<span data-ttu-id="56c31-109">Cuando aplica una directiva de expiración a un equipo, el propietario del equipo recibe una notificación para la renovación del equipo 30 días, 15 días y 1 día antes de la fecha de expiración del equipo.</span><span class="sxs-lookup"><span data-stu-id="56c31-109">When you apply an expiration policy to a team, a team owner receives a notification for team renewal 30 days, 15 days and 1 day before the team's expiration date.</span></span> <span data-ttu-id="56c31-110">Cuando el propietario del equipo reciba la notificación, puede hacer clic en Renovar **ahora** en la configuración del equipo para renovar el equipo.</span><span class="sxs-lookup"><span data-stu-id="56c31-110">When the team owner receives the notification, they can click **Renew now** in team settings to renew the team.</span></span>

<span data-ttu-id="56c31-111">![Captura de pantalla del botón Renovar ahora para renovar un equipo en la configuración del equipo](media/team-expiration.png "Captura de pantalla del botón Renovar ahora para renovar un equipo en la configuración del equipo")</span><span class="sxs-lookup"><span data-stu-id="56c31-111">![Screenshot of the Renew Now button to renew a team in team settings](media/team-expiration.png "Screenshot of the Renew Now button to renew a team in team settings")</span></span>

<span data-ttu-id="56c31-112">Si el propietario del equipo no renueva el equipo y no hay más actividad en el equipo hasta el final de la directiva de expiración, el equipo se pone en estado "eliminado temporalmente", lo que significa que se puede restaurar en los próximos 30 días.</span><span class="sxs-lookup"><span data-stu-id="56c31-112">If the team owner doesn't renew the team and there is no further activity on the team until the end of the expiration policy, the team is put in a "soft-deleted" state, which means it can be restored within the next 30 days.</span></span>

## <a name="team-auto-renewal"></a><span data-ttu-id="56c31-113">Renovación automática del equipo</span><span class="sxs-lookup"><span data-stu-id="56c31-113">Team auto-renewal</span></span>

<span data-ttu-id="56c31-114">Puede haber ocasiones en las que el propietario de un equipo no pueda renovar el equipo tal vez porque olvidó renovarlo o porque estaba fuera cuando vence la renovación.</span><span class="sxs-lookup"><span data-stu-id="56c31-114">There can be times when a team owner is unable to renew the team perhaps because they forgot to renew or were away when renewal was due.</span></span> <span data-ttu-id="56c31-115">En estos escenarios, un equipo en uso activo puede eliminarse debido a las directivas de expiración que se aplican al equipo.</span><span class="sxs-lookup"><span data-stu-id="56c31-115">In these scenarios, a team in active use can get deleted because of expiration policies that apply to the team.</span></span>  

<span data-ttu-id="56c31-116">Para evitar la eliminación accidental, la renovación automática se habilita automáticamente para un equipo de la directiva de expiración del grupo.</span><span class="sxs-lookup"><span data-stu-id="56c31-116">To prevent accidental deletion, auto-renewal is automatically enabled for a team in the group expiration policy.</span></span> <span data-ttu-id="56c31-117">Cuando se configura la directiva de expiración del grupo, cualquier equipo que tenga al menos una visita de canal de cualquier miembro del equipo antes de su fecha de expiración se renueva automáticamente sin la intervención manual del propietario del equipo.</span><span class="sxs-lookup"><span data-stu-id="56c31-117">When the group expiration policy is set up, any team that has at least one channel visit from any team member before its expiration date is automatically renewed without any manual intervention from the team owner.</span></span>

## <a name="known-issues"></a><span data-ttu-id="56c31-118">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="56c31-118">Known issues</span></span>

<span data-ttu-id="56c31-119">**La fecha de expiración del equipo y el grupo subyacente no coinciden**</span><span class="sxs-lookup"><span data-stu-id="56c31-119">**Expiration date of team and underlying group don't match**</span></span>

<span data-ttu-id="56c31-120">Antes de renovar un equipo, el grupo que lo hace se renueva primero.</span><span class="sxs-lookup"><span data-stu-id="56c31-120">Before a team is renewed, the group that backs the team is renewed first.</span></span> <span data-ttu-id="56c31-121">Como parte de la renovación, se establece una nueva fecha de expiración en el grupo para una fecha futura.</span><span class="sxs-lookup"><span data-stu-id="56c31-121">As part of renewal, a new expiry date is set on the group for a future date.</span></span> <span data-ttu-id="56c31-122">Es posible que esta nueva fecha no se pueda ver inmediatamente en Teams.</span><span class="sxs-lookup"><span data-stu-id="56c31-122">This new date may not be immediately visible in Teams.</span></span> <span data-ttu-id="56c31-123">La sincronización puede tardar hasta 24 horas. Si ve una discrepancia entre la fecha de expiración de un equipo y su grupo subyacente, espere 24 horas antes de buscar más soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="56c31-123">It can take up to 24 hours to sync. If you see a discrepancy between the expiry date for a team and its underlying group, wait 24 hours before seeking further support.</span></span>