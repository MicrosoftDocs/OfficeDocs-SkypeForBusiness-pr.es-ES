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
description: Aprenda a usar la búsqueda de directorios de Microsoft Teams en el ámbito para proporcionar vistas personalizadas del directorio.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: ca20e7293f20d68ea98f61a98090f7892ba294e8
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836950"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="1ce4b-103">Usar la búsqueda de directorios enfocada de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1ce4b-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="1ce4b-104">El ámbito de la búsqueda de directorios de Microsoft Teams permite a las organizaciones crear límites virtuales que controlan cómo los usuarios pueden buscar y comunicarse con otros usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="1ce4b-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="1ce4b-105">Microsoft Teams permite a las organizaciones proporcionar vistas personalizadas del directorio a sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="1ce4b-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="1ce4b-106">Microsoft Teams usa [directivas de barrera de información](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) para admitir estas vistas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="1ce4b-106">Microsoft Teams uses [Information Barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) to support these custom views.</span></span> <span data-ttu-id="1ce4b-107">Una vez que se habilitan las directivas, los resultados devueltos por las búsquedas de otros usuarios (por ejemplo, para iniciar una conversación o agregar miembros a un equipo) se regirán según las directivas configuradas.</span><span class="sxs-lookup"><span data-stu-id="1ce4b-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="1ce4b-108">Los usuarios no podrán buscar ni descubrir equipos cuando la búsqueda de ámbito está activa.</span><span class="sxs-lookup"><span data-stu-id="1ce4b-108">Users will not be able to search or discover teams when scoped search is in effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="1ce4b-109">En entornos híbridos de Exchange, esta característica solo funciona con los buzones de Exchange Online y no con los buzones locales.</span><span class="sxs-lookup"><span data-stu-id="1ce4b-109">In Exchange hybrid environments, this feature only works with Exchange Online mailboxes, and not with on-premises mailboxes.</span></span>

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="1ce4b-110">¿Cuándo debería usar búsquedas de directorio de ámbito?</span><span class="sxs-lookup"><span data-stu-id="1ce4b-110">When should you use scoped directory searches?</span></span>

<span data-ttu-id="1ce4b-111">Los escenarios que se benefician de las búsquedas de directorio de ámbito son similares a los escenarios de directiva de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="1ce4b-111">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="1ce4b-112">Por ejemplo, es posible que desee usar la búsqueda de directorios con ámbito en las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="1ce4b-112">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="1ce4b-113">La organización tiene varias compañías en su inquilino, pero prefiere mantenerlas por separado.</span><span class="sxs-lookup"><span data-stu-id="1ce4b-113">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="1ce4b-114">Su centro educativo quiere limitar los chats entre el personal académico y los estudiantes.</span><span class="sxs-lookup"><span data-stu-id="1ce4b-114">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="1ce4b-115">Para obtener información sobre cómo usar las directivas de la libreta de direcciones, lea [directivas de la barrera de información en Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/information-barriers).</span><span class="sxs-lookup"><span data-stu-id="1ce4b-115">To learn how to use address book policies, read [Information Barrier policies in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/information-barriers).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1ce4b-116">Las directivas de la libreta de direcciones proporcionan solo una separación virtual de los usuarios de la perspectiva del directorio.</span><span class="sxs-lookup"><span data-stu-id="1ce4b-116">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="1ce4b-117">Los usuarios pueden seguir iniciando comunicaciones con otras personas proporcionando direcciones de correo electrónico completas.</span><span class="sxs-lookup"><span data-stu-id="1ce4b-117">Users can still initiate communications with others by providing complete email addresses.</span></span> <span data-ttu-id="1ce4b-118">También es importante tener en cuenta que todos los datos de usuario que ya se habían almacenado en la memoria caché antes de la aplicación de directivas de libreta de direcciones nuevas o actualizadas seguirán estando disponibles para los usuarios durante un máximo de 30 días.</span><span class="sxs-lookup"><span data-stu-id="1ce4b-118">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="turn-on-scoped-directory-search"></a><span data-ttu-id="1ce4b-119">Activar la búsqueda de directorio en el ámbito</span><span class="sxs-lookup"><span data-stu-id="1ce4b-119">Turn on scoped directory search</span></span>

1. <span data-ttu-id="1ce4b-120">Use directivas de barrera de información para configurar su organización en subgrupos virtuales.</span><span class="sxs-lookup"><span data-stu-id="1ce4b-120">Use Information Barrier policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="1ce4b-121">Para obtener más información, consulte [definir directivas de barrera](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies)de la información.</span><span class="sxs-lookup"><span data-stu-id="1ce4b-121">For more information, see [Define Information Barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies).</span></span>

2. <span data-ttu-id="1ce4b-122">En el centro de administración de Microsoft Teams, seleccione Configuración de**Teams**de la **organización** > .</span><span class="sxs-lookup"><span data-stu-id="1ce4b-122">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

3. <span data-ttu-id="1ce4b-123">En **Buscar**, junto a la **búsqueda en el directorio de ámbito en Teams mediante una directiva de la libreta de direcciones de Exchange (APB)**, active la opción **de**alternancia.</span><span class="sxs-lookup"><span data-stu-id="1ce4b-123">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (APB)**, turn the toggle **On**.</span></span>

    ![Búsqueda de directorio de ámbito en el centro de administración de Microsoft Teams](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> <span data-ttu-id="1ce4b-125">Este cambio puede demorar hasta 24 horas en replicarse.</span><span class="sxs-lookup"><span data-stu-id="1ce4b-125">This change can take up to 24 hours to replicate.</span></span>
