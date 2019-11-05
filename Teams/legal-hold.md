---
title: Poner a un usuario o un equipo de Microsoft Teams en retención legal
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: Aprenda a poner a un usuario o un equipo de Microsoft Teams en retención legal mediante el Centro de seguridad y cumplimiento, y conozca qué debe poner en retención legal en función de los requisitos de datos.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 25bd8e235be79ed805a854cbda2b4947f1c1269b
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2019
ms.locfileid: "37968041"
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a><span data-ttu-id="8aa42-103">Poner a un usuario o un equipo de Microsoft Teams en retención legal</span><span class="sxs-lookup"><span data-stu-id="8aa42-103">Place a Microsoft Teams user or team on legal hold</span></span>
==================================================

<span data-ttu-id="8aa42-p101">Para poner a un usuario o un equipo en retención legal, navegue al [Centro de seguridad y cumplimiento](https://go.microsoft.com/fwlink/?linkid=854628). Cuando crea un nuevo caso, tiene la opción de poner en retención buzones o sitios.</span><span class="sxs-lookup"><span data-stu-id="8aa42-p101">To put a user or a team on Legal Hold, navigate to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=854628). When you create a new case, you are presented with the option to place mailboxes or sites on hold.</span></span>

> [!NOTE]
> <span data-ttu-id="8aa42-106">Si pone a un usuario en retención, el grupo no se pondrá en retención y viceversa.</span><span class="sxs-lookup"><span data-stu-id="8aa42-106">Placing a user on hold does not automatically place a group on hold or vice-versa.</span></span>

> [!NOTE]
> <span data-ttu-id="8aa42-107">Aún no se admite la configuración de la retención legal de mensajes de canal privado.</span><span class="sxs-lookup"><span data-stu-id="8aa42-107">We don’t yet support configuration for legal hold of private channel messages.</span></span> <span data-ttu-id="8aa42-108">Se admite la retención legal de archivos compartidos en canales privados.</span><span class="sxs-lookup"><span data-stu-id="8aa42-108">Legal hold of files shared in private channels is supported.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8aa42-109">Cuando un usuario o un grupo se pongan en espera, todas las copias de los mensajes se conservarán.</span><span class="sxs-lookup"><span data-stu-id="8aa42-109">When a user or group is placed on hold, all message copies will be retained.</span></span> <span data-ttu-id="8aa42-110">Ejemplo: Clay publicó un mensaje en un canal y luego lo modificó.</span><span class="sxs-lookup"><span data-stu-id="8aa42-110">Example: Clay posted a message in a channel and then modified the message.</span></span> <span data-ttu-id="8aa42-111">En una situación de retención, se retienen las dos copias del mensaje.</span><span class="sxs-lookup"><span data-stu-id="8aa42-111">In a hold scenario, both copies of the message are retained.</span></span> <span data-ttu-id="8aa42-112">Si no hay retención legal, se retiene solo el último mensaje.</span><span class="sxs-lookup"><span data-stu-id="8aa42-112">Without Legal Hold, only the latest message is retained.</span></span>

<span data-ttu-id="8aa42-113">En la imagen de abajo, se está realizando una investigación en torno a Clay.</span><span class="sxs-lookup"><span data-stu-id="8aa42-113">In the figure below, there is an investigation involving Clay.</span></span> <span data-ttu-id="8aa42-114">Clay es miembro del equipo Brokers-Dealers (Agentes distribuidores).</span><span class="sxs-lookup"><span data-stu-id="8aa42-114">Clay is a member of the Brokers-Dealers team.</span></span>

<span data-ttu-id="8aa42-115">Si tuviéramos que poner en retención legal todos los sitios donde Clay pudiera haber hablado sobre planes de intermediación, tendríamos que agregar el sitio de SharePoint del equipo a la lista de sitios en retención legal, además del sitio de OneDrive para la Empresa de Clay.</span><span class="sxs-lookup"><span data-stu-id="8aa42-115">If we needed to Legal Hold all the places Clay could have discussed Brokering plans, ensure that the team’s SharePoint site is added to the Legal Hold site list, as well as Clay’s OneDrive for Business site.</span></span>

![Captura de pantalla de un cuadro de diálogo para crear una nueva retención.](media/Place_a_Microsoft_Teams_user_or_team_on_legal_hold_image3.png)

<span data-ttu-id="8aa42-117">En resumen, vea la tabla de abajo para conocer lo que debe ponerse en retención legal en función de los requisitos de datos:</span><span class="sxs-lookup"><span data-stu-id="8aa42-117">To recap, use the table below to understand what needs to be placed on Legal Hold based on data requirements:</span></span>

|<span data-ttu-id="8aa42-118">Escenario</span><span class="sxs-lookup"><span data-stu-id="8aa42-118">Scenario</span></span>  |<span data-ttu-id="8aa42-119">Qué poner en retención legal</span><span class="sxs-lookup"><span data-stu-id="8aa42-119">What to place on hold</span></span>  |
|---------|---------|
|<span data-ttu-id="8aa42-120">**Chats privados de Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="8aa42-120">**Microsoft Teams Private Chats**</span></span>     |<span data-ttu-id="8aa42-121">Buzón del usuario</span><span class="sxs-lookup"><span data-stu-id="8aa42-121">User mailbox</span></span>         |
|<span data-ttu-id="8aa42-122">**Chats de canal de Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="8aa42-122">**Microsoft Teams Channel Chats**</span></span>    |<span data-ttu-id="8aa42-123">Buzón de grupo usado para el equipo</span><span class="sxs-lookup"><span data-stu-id="8aa42-123">Group mailbox used for the team</span></span>         |
|<span data-ttu-id="8aa42-124">**Contenido de Microsoft Teams (por ejemplo, wiki y archivos)**</span><span class="sxs-lookup"><span data-stu-id="8aa42-124">**Microsoft Teams Content (e.g. Wiki, Files)**</span></span>     |<span data-ttu-id="8aa42-125">Sitio de SharePoint usado por el equipo</span><span class="sxs-lookup"><span data-stu-id="8aa42-125">SharePoint site used by the team</span></span>         |
|<span data-ttu-id="8aa42-126">**Contenido privado**</span><span class="sxs-lookup"><span data-stu-id="8aa42-126">**Private Content**</span></span>     |<span data-ttu-id="8aa42-127">Sitio de OneDrive para la Empresa del usuario</span><span class="sxs-lookup"><span data-stu-id="8aa42-127">OneDrive for Business site of the user</span></span>         |
