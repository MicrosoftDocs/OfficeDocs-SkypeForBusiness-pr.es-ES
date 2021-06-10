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
description: Obtenga información sobre cómo usar Microsoft Teams directorio de ámbito para proporcionar vistas personalizadas del directorio.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1048b6451163cd7b0cdbcd3f52e48c6b0f4811d1
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2021
ms.locfileid: "52717801"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="b35dc-103">Usar la búsqueda de directorios enfocada de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b35dc-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="b35dc-104">Microsoft Teams de directorios de ámbito permite a las organizaciones crear límites virtuales que controlen cómo los usuarios pueden encontrar y comunicarse con otros usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="b35dc-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="b35dc-105">Microsoft Teams permite a las organizaciones proporcionar vistas personalizadas del directorio a sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="b35dc-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="b35dc-106">Microsoft Teams directivas [de Barrera de información](/microsoft-365/compliance/information-barriers) para admitir estas vistas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="b35dc-106">Microsoft Teams uses [Information Barrier policies](/microsoft-365/compliance/information-barriers) to support these custom views.</span></span> <span data-ttu-id="b35dc-107">Una vez habilitadas las directivas, los resultados devueltos por las búsquedas de otros usuarios (por ejemplo, para iniciar un chat o agregar miembros a un equipo) estarán en el ámbito de acuerdo con las directivas configuradas.</span><span class="sxs-lookup"><span data-stu-id="b35dc-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="b35dc-108">Los usuarios no podrán buscar ni descubrir ningún equipo cuando la búsqueda con ámbito esté en vigor, pero los miembros existentes de esos equipos pueden agregar usuarios, tal y como permiten las directivas activas de Barrera de información.</span><span class="sxs-lookup"><span data-stu-id="b35dc-108">Users will not be able to search or discover any teams when scoped search is in effect, but existing members in those teams can add users, as allowed by active Information Barrier policies.</span></span>

> [!NOTE]
> <span data-ttu-id="b35dc-109">En Exchange entornos híbridos, esta característica solo funciona con buzones Exchange Online y no con buzones locales.</span><span class="sxs-lookup"><span data-stu-id="b35dc-109">In Exchange hybrid environments, this feature only works with Exchange Online mailboxes, and not with on-premises mailboxes.</span></span>

<span data-ttu-id="b35dc-110">Vea también [Directivas de libreta de direcciones en Exchange Online](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).</span><span class="sxs-lookup"><span data-stu-id="b35dc-110">See also [Address book policies in Exchange Online](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).</span></span>

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="b35dc-111">¿Cuándo debe usar búsquedas de directorios con ámbito?</span><span class="sxs-lookup"><span data-stu-id="b35dc-111">When should you use scoped directory searches?</span></span>

<span data-ttu-id="b35dc-112">Los escenarios que se benefician de las búsquedas de directorios de ámbito son similares a los escenarios de directiva de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="b35dc-112">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="b35dc-113">Por ejemplo, es posible que desee usar la búsqueda de directorios con ámbito en las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="b35dc-113">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="b35dc-114">La organización tiene varias compañías en su inquilino, pero prefiere mantenerlas por separado.</span><span class="sxs-lookup"><span data-stu-id="b35dc-114">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="b35dc-115">Su centro educativo quiere limitar los chats entre el personal académico y los estudiantes.</span><span class="sxs-lookup"><span data-stu-id="b35dc-115">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="b35dc-116">Para obtener información sobre cómo usar directivas de libreta de direcciones, lea Directivas de barrera de información [en Exchange Online](/microsoft-365/compliance/information-barriers).</span><span class="sxs-lookup"><span data-stu-id="b35dc-116">To learn how to use address book policies, read [Information Barrier policies in Exchange Online](/microsoft-365/compliance/information-barriers).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b35dc-117">Las directivas de libreta de direcciones proporcionan solo una separación virtual de los usuarios de la perspectiva del directorio.</span><span class="sxs-lookup"><span data-stu-id="b35dc-117">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="b35dc-118">También es importante tener en cuenta que los datos de usuario que ya se habían almacenado en caché, antes de la aplicación de directivas de libreta de direcciones nuevas o actualizadas, permanecerán disponibles para los usuarios durante un máximo de 30 días.</span><span class="sxs-lookup"><span data-stu-id="b35dc-118">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="turn-on-scoped-directory-search"></a><span data-ttu-id="b35dc-119">Activar la búsqueda de directorios con ámbito</span><span class="sxs-lookup"><span data-stu-id="b35dc-119">Turn on scoped directory search</span></span>

1. <span data-ttu-id="b35dc-120">Use directivas de Barrera de información para configurar su organización en subgrupos virtuales.</span><span class="sxs-lookup"><span data-stu-id="b35dc-120">Use Information Barrier policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="b35dc-121">Para obtener más información, vea [Definir directivas de barrera de información.](/microsoft-365/compliance/information-barriers-policies)</span><span class="sxs-lookup"><span data-stu-id="b35dc-121">For more information, see [Define Information Barrier policies](/microsoft-365/compliance/information-barriers-policies).</span></span>

2. <span data-ttu-id="b35dc-122">En el Microsoft Teams de administración, seleccione **Configuración de** toda la organización Teams  >  **configuración.**</span><span class="sxs-lookup"><span data-stu-id="b35dc-122">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

3. <span data-ttu-id="b35dc-123">En **Buscar**, junto a Búsqueda de directorio de ámbito en Teams mediante una directiva de libreta de direcciones **(ABP)** de Exchange , active el **botón de alternancia .**</span><span class="sxs-lookup"><span data-stu-id="b35dc-123">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (ABP)**, turn the toggle **On**.</span></span>

    ![Búsqueda de directorios con ámbito en Microsoft Teams de administración](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> <span data-ttu-id="b35dc-125">Este cambio puede tardar unas horas en replicarse.</span><span class="sxs-lookup"><span data-stu-id="b35dc-125">This change can take a few hours to replicate.</span></span>
