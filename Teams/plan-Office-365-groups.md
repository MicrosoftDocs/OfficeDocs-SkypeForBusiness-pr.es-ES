---
title: Planear los grupos de Microsoft 365 cuando se crean equipos
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 08/29/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Obtenga información sobre la planeación de grupos de Microsoft 365 en Teams, incluidas las diferencias entre grupos & conversaciones de Teams y cómo Teams respeta la directiva de nomenclatura de grupos.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: 1acde038bc2df64d7cf35828bf0b08273bf1f095
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51108356"
---
<a name="plan-for-microsoft-365-groups-when-creating-teams-in-microsoft-teams"></a><span data-ttu-id="8b473-103">Planear grupos de Microsoft 365 al crear equipos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8b473-103">Plan for Microsoft 365 Groups when creating teams in Microsoft Teams</span></span>
==========================================================

<span data-ttu-id="8b473-104">Al considerar el uso de grupos de Microsoft 365 o al crear equipos, tenga en cuenta para qué se usará el equipo, quién debe tener acceso y qué resultados espera lograr el equipo.</span><span class="sxs-lookup"><span data-stu-id="8b473-104">When considering the use of Microsoft 365 Groups or when creating teams, consider what the team will be used for, who should have access, and what outcome the team will expect to achieve.</span></span> <span data-ttu-id="8b473-105">Preste especial atención al número de canales que cree, ya que los usuarios pueden desbordarse rápidamente por el contenido extendido demasiado fino (en demasiados canales).</span><span class="sxs-lookup"><span data-stu-id="8b473-105">Pay special attention to the number of channels you create as people can quickly become overrun by content spread too thin (across too many channels).</span></span>

<span data-ttu-id="8b473-106">Hay dos escenarios que justifican cierta discusión sobre la planificación de grupos de Microsoft 365 y su impacto en (o por) Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="8b473-106">There are two scenarios that warrant some discussion around planning of Microsoft 365 Groups and their impact on (or by) Microsoft Teams:</span></span>

-   <span data-ttu-id="8b473-107">En primer lugar, dado que los clientes podrían tener inversiones existentes en Grupos, actualmente se admiten grupos públicos y privados, para el número de miembros admitidos actualmente, consulte Límites y especificaciones de [Microsoft Teams.](./limits-specifications-teams.md)</span><span class="sxs-lookup"><span data-stu-id="8b473-107">First, since customers could have existing investments in Groups, we currently support both Public and Private groups, for the number of members currently supported, please see [Limits and specifications for Microsoft Teams](./limits-specifications-teams.md).</span></span> <span data-ttu-id="8b473-108">Como se mencionó anteriormente, desea administrar la pertenencia de personas a un equipo con el cliente de Teams en lugar del Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8b473-108">As mentioned previously, you want to manage the membership of people to a team using the Teams client rather than the Microsoft 365 admin center.</span></span> <span data-ttu-id="8b473-109">Dado este escenario, si los usuarios están acostumbrados a conversaciones enhebradas en grupos de Microsoft 365, vale la pena tener en cuenta que una conversación de Grupos es esencialmente correo electrónico y no es lo mismo que un mensaje de chat en un canal de Teams.</span><span class="sxs-lookup"><span data-stu-id="8b473-109">Given this scenario, if people are used to threaded conversations in Microsoft 365 Groups, it is worthwhile noting that a Groups conversation is essentially email and not the same as a chat message in a Teams channel.</span></span> <span data-ttu-id="8b473-110">Eduque a los usuarios sobre esta diferencia y sugiera que adopten el formato de mensaje de chat más flexible en Teams, en lugar de enviar un correo electrónico al grupo con Outlook o OWA.</span><span class="sxs-lookup"><span data-stu-id="8b473-110">Educate your people about this difference and suggest they adopt the more flexible chat message format in Teams versus emailing the Group using Outlook or OWA.</span></span>

-   <span data-ttu-id="8b473-111">En segundo lugar, para los clientes que no tienen grupos existentes definidos en Microsoft 365, puede crearlos con el Centro de administración de Microsoft 365, la web de Teams o los clientes de escritorio.</span><span class="sxs-lookup"><span data-stu-id="8b473-111">Second, for customers who don't have existing Groups defined in Microsoft 365, you can either create them using the Microsoft 365 admin center, the Teams web, or desktop clients.</span></span> <span data-ttu-id="8b473-112">Como se mencionó anteriormente, administre toda la pertenencia futura al grupo de Microsoft 365 con el cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="8b473-112">As mentioned previously, manage all future membership to the Microsoft 365 group using the Teams client.</span></span> <span data-ttu-id="8b473-113">Dado que la pertenencia a un equipo también está definiendo la pertenencia a grupos de Microsoft 365, debe preparar a los usuarios para este cambio.</span><span class="sxs-lookup"><span data-stu-id="8b473-113">Since membership to a team is also defining membership to Microsoft 365 Groups, you should prepare people for this change.</span></span>

## <a name="teams-respects-microsoft-365-groups-naming-policy-in-private-preview"></a><span data-ttu-id="8b473-114">Teams respeta la directiva de nomenclatura grupos de Microsoft 365 (en versión preliminar privada)</span><span class="sxs-lookup"><span data-stu-id="8b473-114">Teams respects Microsoft 365 Groups naming policy (in private preview)</span></span>

<span data-ttu-id="8b473-115">Cualquier directiva de nomenclatura de grupos de Microsoft 365 que haya establecido el administrador se aplicará en Teams cuando los usuarios creen o editan nombres de equipo.</span><span class="sxs-lookup"><span data-stu-id="8b473-115">Any Microsoft 365 Groups naming policy that has been set by your admin will be applied in Teams when users create or edit team names.</span></span> <span data-ttu-id="8b473-116">En ella se incluyen cosas como los sufijos y los prefijos obligatorios y la exclusión de palabras prohibidas.</span><span class="sxs-lookup"><span data-stu-id="8b473-116">This includes things like mandatory prefixes or suffixes and excluding banned words.</span></span>

> [!NOTE]
> <span data-ttu-id="8b473-117">Esta característica está en versión preliminar privada, lo que significa que, si no forma parte de esta vista previa, Teams aún no se adhiere a esta directiva de nomenclatura de grupos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8b473-117">This feature is in private preview, which means that if you're not part of this preview, Teams doesn't yet adhere to this Microsoft 365 Groups naming policy.</span></span>

<span data-ttu-id="8b473-118">Para obtener más información, lea Directiva de nomenclatura de [grupos de Microsoft 365 en Teams.](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)</span><span class="sxs-lookup"><span data-stu-id="8b473-118">To learn more, read [Microsoft 365 Groups naming policy in Teams](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>

<span data-ttu-id="8b473-119">Los siguientes artículos son un buen lugar para encontrar contenido de preparación y adopción para los grupos de Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="8b473-119">The following articles are a good place to find readiness and adoption content for your Microsoft 365 Groups:</span></span>

-   [<span data-ttu-id="8b473-120">Obtener más con grupos en Outlook</span><span class="sxs-lookup"><span data-stu-id="8b473-120">Get more with groups in Outlook</span></span>](https://support.office.com/article/Get-more-with-Office-365-Groups-in-Outlook-93132800-5b11-49de-8cc2-605b6075b2b9)

-   [<span data-ttu-id="8b473-121">Agregar o quitar miembros de grupos de Microsoft 365 con el Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8b473-121">Add or remove members from Microsoft 365 Groups using the Microsoft 365 admin center</span></span>](https://support.office.com/article/Manage-Group-membership-in-the-Office-365-admin-center-e186d224-a324-4afa-8300-0e4fc0c3000a)

-   [<span data-ttu-id="8b473-122">Restaurar un grupo eliminado</span><span class="sxs-lookup"><span data-stu-id="8b473-122">Restore a deleted group</span></span>](/microsoft-365/admin/create-groups/restore-deleted-group)