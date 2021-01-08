---
title: Usar la búsqueda de directorios enfocada de Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Aprenda a usar la búsqueda en el directorio de ámbito de Microsoft Teams para proporcionar vistas personalizadas del directorio.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4f478bba8c396f0f20b95f69f56c2ded556224d
ms.sourcegitcommit: 2300595db7779da7a127ae9ee16e474452df02d3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2021
ms.locfileid: "49779934"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="d3d26-103">Usar la búsqueda de directorios enfocada de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d3d26-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="d3d26-104">La búsqueda en el directorio de ámbito de Microsoft Teams permite a las organizaciones crear límites virtuales que controlan la forma en que los usuarios pueden encontrar y comunicarse con otros usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="d3d26-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="d3d26-105">Microsoft Teams permite a las organizaciones proporcionar vistas personalizadas del directorio a sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="d3d26-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="d3d26-106">Microsoft Teams usa directivas [de Barrera de la](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) información para admitir estas vistas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="d3d26-106">Microsoft Teams uses [Information Barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) to support these custom views.</span></span> <span data-ttu-id="d3d26-107">Una vez habilitadas las directivas, los resultados devueltos por las búsquedas de otros usuarios (por ejemplo, para iniciar un chat o agregar miembros a un equipo) estarán en el ámbito según las directivas configuradas.</span><span class="sxs-lookup"><span data-stu-id="d3d26-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="d3d26-108">Los usuarios no podrán buscar o descubrir equipos cuando la búsqueda de ámbito esté en vigor.</span><span class="sxs-lookup"><span data-stu-id="d3d26-108">Users will not be able to search or discover teams when scoped search is in effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="d3d26-109">En entornos híbridos de Exchange, esta característica solo funciona con buzones de Exchange Online y no con buzones locales.</span><span class="sxs-lookup"><span data-stu-id="d3d26-109">In Exchange hybrid environments, this feature only works with Exchange Online mailboxes, and not with on-premises mailboxes.</span></span>

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="d3d26-110">¿Cuándo debería usar búsquedas en directorios de ámbito?</span><span class="sxs-lookup"><span data-stu-id="d3d26-110">When should you use scoped directory searches?</span></span>

<span data-ttu-id="d3d26-111">Los escenarios que se benefician de las búsquedas en directorios de ámbito son similares a los escenarios de directivas de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="d3d26-111">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="d3d26-112">Por ejemplo, es posible que desee usar búsqueda en el directorio de ámbito en las situaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="d3d26-112">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="d3d26-113">La organización tiene varias compañías en su inquilino, pero prefiere mantenerlas por separado.</span><span class="sxs-lookup"><span data-stu-id="d3d26-113">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="d3d26-114">Su centro educativo quiere limitar los chats entre el personal académico y los estudiantes.</span><span class="sxs-lookup"><span data-stu-id="d3d26-114">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="d3d26-115">Para obtener información sobre cómo usar las directivas de la libreta de direcciones, lea las directivas de Barrera de [la información en Exchange Online.](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)</span><span class="sxs-lookup"><span data-stu-id="d3d26-115">To learn how to use address book policies, read [Information Barrier policies in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/information-barriers).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d3d26-116">Las directivas de libreta de direcciones proporcionan solo una separación virtual de los usuarios desde la perspectiva del directorio.</span><span class="sxs-lookup"><span data-stu-id="d3d26-116">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="d3d26-117">También es importante tener en cuenta que los datos de usuario que ya se almacenaron en caché, antes de aplicar directivas de libreta de direcciones nuevas o actualizadas, permanecerán disponibles para los usuarios durante un máximo de 30 días.</span><span class="sxs-lookup"><span data-stu-id="d3d26-117">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="turn-on-scoped-directory-search"></a><span data-ttu-id="d3d26-118">Activar búsqueda de directorios de ámbito</span><span class="sxs-lookup"><span data-stu-id="d3d26-118">Turn on scoped directory search</span></span>

1. <span data-ttu-id="d3d26-119">Use las directivas de Barrera de información para configurar su organización en subgrupos virtuales.</span><span class="sxs-lookup"><span data-stu-id="d3d26-119">Use Information Barrier policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="d3d26-120">Para obtener más información, vea [Definir directivas de barreras de información.](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies)</span><span class="sxs-lookup"><span data-stu-id="d3d26-120">For more information, see [Define Information Barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies).</span></span>

2. <span data-ttu-id="d3d26-121">En el Centro de administración de Microsoft Teams, seleccione **configuración de Teams** para toda la  >  **organización.**</span><span class="sxs-lookup"><span data-stu-id="d3d26-121">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

3. <span data-ttu-id="d3d26-122">En **Búsqueda,** junto a Búsqueda en el directorio Ámbito en Teams con una directiva de libreta de direcciones de **Exchange (ABP),** active el botón de **alternancia.**</span><span class="sxs-lookup"><span data-stu-id="d3d26-122">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (ABP)**, turn the toggle **On**.</span></span>

    ![Búsqueda de directorios de ámbito en el Centro de administración de Microsoft Teams](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> <span data-ttu-id="d3d26-124">Este cambio puede tardar unas horas en replicarse.</span><span class="sxs-lookup"><span data-stu-id="d3d26-124">This change can take a few hours to replicate.</span></span>
