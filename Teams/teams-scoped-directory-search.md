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
description: Obtenga información sobre cómo usar la búsqueda de directorios de ámbito de Microsoft Teams para proporcionar vistas personalizadas del directorio.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: b1ba7de8cea23efc23f1eaa6c568d87b0d3ec750
ms.sourcegitcommit: e29e38bf00536400e5826fc55bc86dfd6ed761f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2021
ms.locfileid: "50558329"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="89ac5-103">Usar la búsqueda de directorios enfocada de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="89ac5-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="89ac5-104">La búsqueda de directorios de ámbito de Microsoft Teams permite a las organizaciones crear límites virtuales que controlen cómo los usuarios pueden encontrar y comunicarse con otros usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="89ac5-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="89ac5-105">Microsoft Teams permite a las organizaciones proporcionar vistas personalizadas del directorio a sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="89ac5-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="89ac5-106">Microsoft Teams usa [directivas de Barrera de información](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) para admitir estas vistas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="89ac5-106">Microsoft Teams uses [Information Barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) to support these custom views.</span></span> <span data-ttu-id="89ac5-107">Una vez habilitadas las directivas, los resultados devueltos por las búsquedas de otros usuarios (por ejemplo, para iniciar un chat o agregar miembros a un equipo) estarán en el ámbito de acuerdo con las directivas configuradas.</span><span class="sxs-lookup"><span data-stu-id="89ac5-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="89ac5-108">Los usuarios no podrán buscar ni descubrir ningún equipo cuando la búsqueda con ámbito esté en vigor, pero los miembros existentes de esos equipos pueden agregar usuarios, tal y como permiten las directivas activas de Barrera de información.</span><span class="sxs-lookup"><span data-stu-id="89ac5-108">Users will not be able to search or discover any teams when scoped search is in effect, but existing members in those teams can add users, as allowed by active Information Barrier policies.</span></span>

> [!NOTE]
> <span data-ttu-id="89ac5-109">En entornos híbridos de Exchange, esta característica solo funciona con buzones de Exchange Online y no con buzones locales.</span><span class="sxs-lookup"><span data-stu-id="89ac5-109">In Exchange hybrid environments, this feature only works with Exchange Online mailboxes, and not with on-premises mailboxes.</span></span>

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="89ac5-110">¿Cuándo debe usar búsquedas de directorios con ámbito?</span><span class="sxs-lookup"><span data-stu-id="89ac5-110">When should you use scoped directory searches?</span></span>

<span data-ttu-id="89ac5-111">Los escenarios que se benefician de las búsquedas de directorios de ámbito son similares a los escenarios de directiva de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="89ac5-111">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="89ac5-112">Por ejemplo, es posible que desee usar la búsqueda de directorios con ámbito en las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="89ac5-112">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="89ac5-113">La organización tiene varias compañías en su inquilino, pero prefiere mantenerlas por separado.</span><span class="sxs-lookup"><span data-stu-id="89ac5-113">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="89ac5-114">Su centro educativo quiere limitar los chats entre el personal académico y los estudiantes.</span><span class="sxs-lookup"><span data-stu-id="89ac5-114">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="89ac5-115">Para obtener información sobre cómo usar directivas de libreta de direcciones, lea [Directivas de barrera de información en Exchange Online.](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)</span><span class="sxs-lookup"><span data-stu-id="89ac5-115">To learn how to use address book policies, read [Information Barrier policies in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/information-barriers).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="89ac5-116">Las directivas de libreta de direcciones proporcionan solo una separación virtual de los usuarios de la perspectiva del directorio.</span><span class="sxs-lookup"><span data-stu-id="89ac5-116">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="89ac5-117">También es importante tener en cuenta que los datos de usuario que ya se habían almacenado en caché, antes de la aplicación de directivas de libreta de direcciones nuevas o actualizadas, permanecerán disponibles para los usuarios durante un máximo de 30 días.</span><span class="sxs-lookup"><span data-stu-id="89ac5-117">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="turn-on-scoped-directory-search"></a><span data-ttu-id="89ac5-118">Activar la búsqueda de directorios con ámbito</span><span class="sxs-lookup"><span data-stu-id="89ac5-118">Turn on scoped directory search</span></span>

1. <span data-ttu-id="89ac5-119">Use directivas de Barrera de información para configurar su organización en subgrupos virtuales.</span><span class="sxs-lookup"><span data-stu-id="89ac5-119">Use Information Barrier policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="89ac5-120">Para obtener más información, vea [Definir directivas de barrera de información.](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies)</span><span class="sxs-lookup"><span data-stu-id="89ac5-120">For more information, see [Define Information Barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies).</span></span>

2. <span data-ttu-id="89ac5-121">En el Centro de administración de Microsoft Teams, seleccione Configuración de Teams **para toda la**  >  **organización.**</span><span class="sxs-lookup"><span data-stu-id="89ac5-121">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

3. <span data-ttu-id="89ac5-122">En **Buscar**, junto a Búsqueda de directorio de ámbito en Teams con una directiva de libreta de direcciones **de Exchange (ABP),** active el botón de **alternancia**.</span><span class="sxs-lookup"><span data-stu-id="89ac5-122">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (ABP)**, turn the toggle **On**.</span></span>

    ![Búsqueda de directorios con ámbito en el Centro de administración de Microsoft Teams](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> <span data-ttu-id="89ac5-124">Este cambio puede tardar unas horas en replicarse.</span><span class="sxs-lookup"><span data-stu-id="89ac5-124">This change can take a few hours to replicate.</span></span>
