---
title: Usar la búsqueda de directorios enfocada de Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
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
- Teams_ITAdmin_Help
description: Aprenda a usar la búsqueda de directorios de Microsoft Teams en el ámbito para proporcionar vistas personalizadas del directorio.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: bf65cec72c21e34e0aab8338d20ae36549497846
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221734"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="ca788-103">Usar la búsqueda de directorios enfocada de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ca788-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="ca788-104">El ámbito de la búsqueda de directorios de Microsoft Teams permite a las organizaciones crear límites virtuales que controlan cómo los usuarios pueden buscar y comunicarse con otros usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="ca788-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="ca788-105">Microsoft Teams permite a las organizaciones proporcionar vistas personalizadas del directorio a sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="ca788-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="ca788-106">Microsoft Teams usa [directivas de libreta de direcciones de Exchange](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) para admitir estas vistas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="ca788-106">Microsoft Teams uses [Exchange address book policies](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) to support these custom views.</span></span> <span data-ttu-id="ca788-107">Una vez que se habilitan las directivas, los resultados devueltos por las búsquedas de otros usuarios (por ejemplo, para iniciar una conversación o agregar miembros a un equipo) se regirán según las directivas configuradas.</span><span class="sxs-lookup"><span data-stu-id="ca788-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="ca788-108">Los usuarios no podrán buscar ni descubrir equipos cuando la búsqueda de ámbito está activa.</span><span class="sxs-lookup"><span data-stu-id="ca788-108">Users will not be able to search or discover teams when scoped search is in effect.</span></span> 

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="ca788-109">¿Cuándo debería usar búsquedas de directorio de ámbito?</span><span class="sxs-lookup"><span data-stu-id="ca788-109">When should you use scoped directory searches?</span></span>

<span data-ttu-id="ca788-110">Los escenarios que se benefician de las búsquedas de directorio de ámbito son similares a los escenarios de directiva de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="ca788-110">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="ca788-111">Por ejemplo, es posible que desee usar la búsqueda de directorios con ámbito en las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="ca788-111">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="ca788-112">La organización tiene varias compañías en su inquilino, pero prefiere mantenerlas por separado.</span><span class="sxs-lookup"><span data-stu-id="ca788-112">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="ca788-113">Su centro educativo quiere limitar los chats entre el personal académico y los estudiantes.</span><span class="sxs-lookup"><span data-stu-id="ca788-113">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="ca788-114">Para obtener información sobre cómo usar las directivas de la libreta de direcciones, lea [directivas de libreta de direcciones en Exchange Online](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).</span><span class="sxs-lookup"><span data-stu-id="ca788-114">To learn how to use address book policies, read [Address book policies in Exchange Online](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ca788-115">Las directivas de la libreta de direcciones proporcionan solo una separación virtual de los usuarios de la perspectiva del directorio.</span><span class="sxs-lookup"><span data-stu-id="ca788-115">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="ca788-116">Los usuarios pueden seguir iniciando comunicaciones con otras personas proporcionando direcciones de correo electrónico completas.</span><span class="sxs-lookup"><span data-stu-id="ca788-116">Users can still initiate communications with others by providing complete email addresses.</span></span> <span data-ttu-id="ca788-117">También es importante tener en cuenta que todos los datos de usuario que ya se habían almacenado en la memoria caché antes de la aplicación de directivas de libreta de direcciones nuevas o actualizadas seguirán estando disponibles para los usuarios durante un máximo de 30 días.</span><span class="sxs-lookup"><span data-stu-id="ca788-117">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="turn-on-scoped-directory-search"></a><span data-ttu-id="ca788-118">Activar la búsqueda de directorio en el ámbito</span><span class="sxs-lookup"><span data-stu-id="ca788-118">Turn on scoped directory search</span></span>

1. <span data-ttu-id="ca788-119">Use directivas de libreta de direcciones para configurar su organización en subgrupos virtuales.</span><span class="sxs-lookup"><span data-stu-id="ca788-119">Use address book policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="ca788-120">Para obtener más información, consulte [procedimientos para directivas de libreta de direcciones](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).</span><span class="sxs-lookup"><span data-stu-id="ca788-120">For more information, see [Procedures for address book policies](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies).</span></span>

2. <span data-ttu-id="ca788-121">En el centro de administración de Microsoft Teams, seleccione Configuración de Teams de la **organización** > \*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="ca788-121">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

3. <span data-ttu-id="ca788-122">En **Buscar**, junto a la **búsqueda en el directorio de ámbito en Teams mediante una directiva de la libreta de direcciones de Exchange (APB)**, active la opción **de**alternancia.</span><span class="sxs-lookup"><span data-stu-id="ca788-122">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (APB)**, turn the toggle **On**.</span></span>

    ![Búsqueda de directorio de ámbito en el centro de administración de Microsoft Teams](media/teams-scoped-directory-search-image1.png)

> [!NOTE]
> <span data-ttu-id="ca788-124">Las configuraciones híbridas (equipos con Exchange local) no admiten el modo de búsqueda de ámbito.</span><span class="sxs-lookup"><span data-stu-id="ca788-124">Hybrid configurations (Teams with Exchange on-premises) do not support scoped search mode.</span></span> 

