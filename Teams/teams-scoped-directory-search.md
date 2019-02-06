---
title: Usar la búsqueda de directorios enfocada de Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/09/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo usar búsqueda de Active directory con ámbito de Microsoft Teams para proporcionar vistas personalizadas del directorio.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a4a36de9b535d7c95f93175a97ce5266fdc37ec
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754310"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="6ebc7-103">Usar la búsqueda de directorios enfocada de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6ebc7-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="6ebc7-104">Búsqueda en el directorio con ámbito Microsoft Teams permite a las organizaciones crear límites virtuales que controlan cómo los usuarios pueden encontrar y comunicarse con otros usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="6ebc7-105">Microsoft Teams permite a las organizaciones a proporcionar vistas personalizadas del directorio a sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="6ebc7-106">Microsoft Teams usa [directivas de la libreta de direcciones de Exchange](https://docs.microsoft.com/Exchange/email-addresses-and-address-books/address-book-policies/address-book-policies?view=exchserver-2019) para admitir estas vistas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-106">Microsoft Teams uses [Exchange address book policies](https://docs.microsoft.com/Exchange/email-addresses-and-address-books/address-book-policies/address-book-policies?view=exchserver-2019) to support these custom views.</span></span> <span data-ttu-id="6ebc7-107">Una vez que las directivas están habilitadas, se limita los resultados devueltos por las búsquedas para otros usuarios (por ejemplo, para iniciar una charla o para agregar a miembros a un equipo) según las directivas configuradas.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="6ebc7-108">Los usuarios no podrán buscar o detectar los equipos al ámbito de búsqueda está en vigor.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-108">Users will not be able to search or discover teams when scoped search is in effect.</span></span> 

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="6ebc7-109">¿Cuándo se debe utilizar las búsquedas de directorio con ámbito?</span><span class="sxs-lookup"><span data-stu-id="6ebc7-109">When should you use scoped directory searches?</span></span>

<span data-ttu-id="6ebc7-110">Escenarios que se benefician de las búsquedas de directorio con ámbito son similares a los escenarios de directiva de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-110">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="6ebc7-111">Por ejemplo, es posible que desee usar la búsqueda en el directorio con ámbito en las situaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="6ebc7-111">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="6ebc7-112">La organización tiene varias compañías en su inquilino, pero prefiere mantenerlas por separado.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-112">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="6ebc7-113">Su centro educativo quiere limitar los chats entre el personal académico y los estudiantes.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-113">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="6ebc7-114">Encontrará más información acerca de cómo se pueden usar las directivas de la libreta de direcciones [aquí](https://docs.microsoft.com/Exchange/email-addresses-and-address-books/address-book-policies/abp-scenarios?view=exchserver-2019).</span><span class="sxs-lookup"><span data-stu-id="6ebc7-114">You can learn more about how address book policies can be used [here](https://docs.microsoft.com/Exchange/email-addresses-and-address-books/address-book-policies/abp-scenarios?view=exchserver-2019).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6ebc7-115">Directivas de la libreta de direcciones proporcionan sólo una virtual separación de los usuarios desde la perspectiva de Active directory.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-115">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="6ebc7-116">Los usuarios aún pueden iniciar comunicaciones con otros usuarios proporcionando direcciones de correo electrónico completa.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-116">Users can still initiate communications with others by providing complete email addresses.</span></span> <span data-ttu-id="6ebc7-117">También es importante tener en cuenta que los datos de usuario que tenían ya ha almacenado en caché, antes de la aplicación de directivas de la libreta de direcciones nuevos o actualizados, permanecerá disponibles para los usuarios de hasta 30 días.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-117">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="enable-scoped-directory-search"></a><span data-ttu-id="6ebc7-118">Habilitar la búsqueda de Active directory con ámbito</span><span class="sxs-lookup"><span data-stu-id="6ebc7-118">Enable scoped directory search</span></span>

1.  <span data-ttu-id="6ebc7-119">Usar directivas de la libreta de direcciones para configurar su organización en subgrupos virtuales.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-119">Use address book policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="6ebc7-120">Para obtener más información, vea [procedimientos para directivas de la libreta de direcciones](https://docs.microsoft.com/Exchange/email-addresses-and-address-books/address-book-policies/abp-procedures?view=exchserver-2019).</span><span class="sxs-lookup"><span data-stu-id="6ebc7-120">For more information, see [Procedures for address book policies](https://docs.microsoft.com/Exchange/email-addresses-and-address-books/address-book-policies/abp-procedures?view=exchserver-2019).</span></span>

2.  <span data-ttu-id="6ebc7-121">Inicie sesión en el centro de administración de Microsoft 365, seleccione **centros de administración**y, a continuación, seleccione **los equipos & Skype**.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-121">Sign in to the Microsoft 365 admin center, select **Admin centers**, and then select **Teams & Skype**.</span></span>
 
3.  <span data-ttu-id="6ebc7-122">En el centro de administración de Microsoft Teams, seleccione **configuración de toda la organización** > **configuración de los equipos**.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-122">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

4.  <span data-ttu-id="6ebc7-123">En la **búsqueda**, junto a **búsqueda de Active directory de ámbito en los equipos mediante una directiva de la libreta de direcciones de Exchange (APB)**, activar la alternancia **en**.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-123">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (APB)**, turn the toggle **On**.</span></span> 

    ![Ámbito de búsqueda en el directorio en el centro de administración de Microsoft Teams](media/teams-scoped-directory-search-image1.png)

> [!NOTE]
> <span data-ttu-id="6ebc7-125">Configuraciones híbridas (los equipos con Exchange local) no admiten el modo de búsqueda con un ámbito.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-125">Hybrid configurations (Teams with Exchange on-premises) do not support scoped search mode.</span></span> 

