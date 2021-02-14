---
title: Renovación y expiración del equipo en Microsoft Teams
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
description: Obtenga información sobre la expiración y renovación del equipo y cómo usar la directiva de expiración de grupos de Microsoft 365 para limpiar automáticamente los equipos sin usar en Microsoft Teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: b111ddd6b874fef22a7d221f6eb932c4c14c7b70
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809410"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a><span data-ttu-id="cff4a-103">Renovación y expiración del equipo en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cff4a-103">Team expiration and renewal in Microsoft Teams</span></span>

<span data-ttu-id="cff4a-104">Las organizaciones con un gran número de equipos a menudo tienen equipos que nunca se usan realmente.</span><span class="sxs-lookup"><span data-stu-id="cff4a-104">Organizations with a large number of teams often have teams that are never actually used.</span></span> <span data-ttu-id="cff4a-105">Esto puede suceder por varios motivos, como la experimentación de productos, la colaboración en equipo a corto plazo o la salida de los propietarios de equipos de la organización.</span><span class="sxs-lookup"><span data-stu-id="cff4a-105">This can happen because of several reasons including product experimentation, short-term team collaboration, or team owners leaving the organization.</span></span> <span data-ttu-id="cff4a-106">Con el tiempo, estos equipos pueden acumular y generar una carga en los recursos de inquilino.</span><span class="sxs-lookup"><span data-stu-id="cff4a-106">Over time, such teams can accumulate and create a burden on tenant resources.</span></span>  

<span data-ttu-id="cff4a-107">Como administrador, puede usar la directiva de expiración del grupo de [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) para controlar el número de equipos sin usar.</span><span class="sxs-lookup"><span data-stu-id="cff4a-107">To curb the number of unused teams, as an admin, you can use [Microsoft 365 group expiration policy](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) to automatically clean up unused teams.</span></span> <span data-ttu-id="cff4a-108">Dado que los grupos tienen copia de seguridad de los equipos, las directivas de expiración de grupo también se aplican automáticamente a los equipos.</span><span class="sxs-lookup"><span data-stu-id="cff4a-108">Because teams are backed by groups, group expiration policies automatically apply to teams as well.</span></span>

<span data-ttu-id="cff4a-109">Cuando aplica una directiva de expiración a un equipo, el propietario del equipo recibe una notificación de renovación del equipo 30 días, 15 días y 1 día antes de la fecha de expiración del equipo.</span><span class="sxs-lookup"><span data-stu-id="cff4a-109">When you apply an expiration policy to a team, a team owner receives a notification for team renewal 30 days, 15 days and 1 day before the team's expiration date.</span></span> <span data-ttu-id="cff4a-110">Cuando el propietario del equipo reciba la notificación, puede hacer clic en Renovar **ahora** en la configuración del equipo para renovar el equipo.</span><span class="sxs-lookup"><span data-stu-id="cff4a-110">When the team owner receives the notification, they can click **Renew now** in team settings to renew the team.</span></span>

<span data-ttu-id="cff4a-111">![Captura de pantalla del botón Renovar ahora para renovar un equipo en la configuración del equipo](media/team-expiration.png "Captura de pantalla del botón Renovar ahora para renovar un equipo en la configuración del equipo")</span><span class="sxs-lookup"><span data-stu-id="cff4a-111">![Screenshot of the Renew Now button to renew a team in team settings](media/team-expiration.png "Screenshot of the Renew Now button to renew a team in team settings")</span></span>

<span data-ttu-id="cff4a-112">Si el propietario del equipo no renueva el equipo y no hay ninguna actividad más en el equipo hasta el final de la directiva de expiración, el equipo se pone en el estado "eliminado temporalmente", lo que significa que se puede restaurar en los próximos 30 días.</span><span class="sxs-lookup"><span data-stu-id="cff4a-112">If the team owner doesn't renew the team and there is no further activity on the team until the end of the expiration policy, the team is put in a "soft-deleted" state, which means it can be restored within the next 30 days.</span></span>

## <a name="team-auto-renewal"></a><span data-ttu-id="cff4a-113">Renovación automática de Team</span><span class="sxs-lookup"><span data-stu-id="cff4a-113">Team auto-renewal</span></span>

<span data-ttu-id="cff4a-114">Puede haber ocasiones en las que el propietario de un equipo no pueda renovar el equipo, quizás porque se olvidó de renovar o porque estaba fuera cuando hubo renovación.</span><span class="sxs-lookup"><span data-stu-id="cff4a-114">There can be times when a team owner is unable to renew the team perhaps because they forgot to renew or were away when renewal was due.</span></span> <span data-ttu-id="cff4a-115">En estos escenarios, un equipo en uso activo puede eliminarse debido a las directivas de expiración que se aplican al equipo.</span><span class="sxs-lookup"><span data-stu-id="cff4a-115">In these scenarios, a team in active use can get deleted because of expiration policies that apply to the team.</span></span>  

<span data-ttu-id="cff4a-116">Para evitar la eliminación accidental, la renovación automática se habilita automáticamente para un equipo en la directiva de expiración del grupo.</span><span class="sxs-lookup"><span data-stu-id="cff4a-116">To prevent accidental deletion, auto-renewal is automatically enabled for a team in the group expiration policy.</span></span> <span data-ttu-id="cff4a-117">Cuando se configura la directiva de expiración del grupo, cualquier equipo que tenga al menos una visita de canal de cualquier miembro del equipo antes de su fecha de expiración se renueva automáticamente sin la intervención manual del propietario del equipo.</span><span class="sxs-lookup"><span data-stu-id="cff4a-117">When the group expiration policy is set up, any team that has at least one channel visit from any team member before its expiration date is automatically renewed without any manual intervention from the team owner.</span></span>

## <a name="known-issues"></a><span data-ttu-id="cff4a-118">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="cff4a-118">Known issues</span></span>

<span data-ttu-id="cff4a-119">**La fecha de expiración del equipo y el grupo subyacente no coinciden**</span><span class="sxs-lookup"><span data-stu-id="cff4a-119">**Expiration date of team and underlying group don't match**</span></span>

<span data-ttu-id="cff4a-120">Antes de renovar un equipo, el grupo que lo hace se renueva en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="cff4a-120">Before a team is renewed, the group that backs the team is renewed first.</span></span> <span data-ttu-id="cff4a-121">Como parte de la renovación, se establece una nueva fecha de vencimiento en el grupo para una fecha futura.</span><span class="sxs-lookup"><span data-stu-id="cff4a-121">As part of renewal, a new expiry date is set on the group for a future date.</span></span> <span data-ttu-id="cff4a-122">Es posible que esta nueva fecha no se pueda ver inmediatamente en Teams.</span><span class="sxs-lookup"><span data-stu-id="cff4a-122">This new date may not be immediately visible in Teams.</span></span> <span data-ttu-id="cff4a-123">La sincronización puede tardar hasta 24 horas. Si ve una discrepancia entre la fecha de vencimiento de un equipo y su grupo subyacente, espere 24 horas antes de solicitar más soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="cff4a-123">It can take up to 24 hours to sync. If you see a discrepancy between the expiry date for a team and its underlying group, wait 24 hours before seeking further support.</span></span>
