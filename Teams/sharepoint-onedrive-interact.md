---
title: Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint Online & interacción de OneDrive para la Empresa con Teams; Almacenamiento privado de archivos de chat & interacción entre equipo, canal estándar, & biblioteca de documentos.
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2d063cae8b87ffcacd63676da17fc000384c432c
ms.sourcegitcommit: a731226d62d8b23fe73bd7bf61654e16367fbd90
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2021
ms.locfileid: "51948633"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="144df-103">Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="144df-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="144df-104">Vea la siguiente sesión para obtener información sobre cómo Teams interactúa con Azure Active Directory (AAD), Grupos de Microsoft 365, Exchange, SharePoint y OneDrive para la Empresa: [Conceptos básicos de Microsoft Teams](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="144df-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Microsoft 365 Groups, Exchange, SharePoint and OneDrive for Business: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="144df-105">Cada equipo de Microsoft Teams tiene un sitio de grupo en SharePoint Online y cada canal estándar de un equipo obtiene una carpeta dentro de la biblioteca de documentos predeterminada del sitio de grupo.</span><span class="sxs-lookup"><span data-stu-id="144df-105">Each team in Microsoft Teams has a team site in SharePoint Online, and each standard channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="144df-106">Los archivos compartidos en una conversación se agregan automáticamente a la biblioteca de documentos y los permisos y las opciones de seguridad de archivos establecidas en SharePoint se reflejan automáticamente en Teams.</span><span class="sxs-lookup"><span data-stu-id="144df-106">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span> <span data-ttu-id="144df-107">Para ver el impacto de cambiar una dirección de sitio en SharePoint, lea [Cambiar una dirección de sitio.](/sharepoint/change-site-address)</span><span class="sxs-lookup"><span data-stu-id="144df-107">To see the impact of changing a site address in SharePoint, read [Change a site address](/sharepoint/change-site-address).</span></span>

> [!NOTE]
> <span data-ttu-id="144df-108">Este artículo solo se aplica a los canales estándar.</span><span class="sxs-lookup"><span data-stu-id="144df-108">This article applies only to standard channels.</span></span> <span data-ttu-id="144df-109">La arquitectura de los canales privados es diferente de los canales estándar.</span><span class="sxs-lookup"><span data-stu-id="144df-109">The architecture for private channels is different from standard channels.</span></span> <span data-ttu-id="144df-110">Cada canal privado tiene su propia colección de sitios de SharePoint independiente del sitio de grupo principal.</span><span class="sxs-lookup"><span data-stu-id="144df-110">Each private channel has its own SharePoint site collection that's separate from the parent team site.</span></span> <span data-ttu-id="144df-111">Para obtener más información, vea [Canales privados en Microsoft Teams.](private-channels.md)</span><span class="sxs-lookup"><span data-stu-id="144df-111">To learn more, see [Private channels in Microsoft Teams](private-channels.md).</span></span>

<span data-ttu-id="144df-112">Los archivos de chat privados se almacenan en la carpeta de OneDrive para la Empresa del remitente y los permisos se conceden automáticamente a todos los participantes como parte del proceso de uso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="144df-112">Private chat files are stored in the sender's OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="144df-113">Si a los usuarios no se les asigna ni se les habilita licencias de SharePoint Online, no tendrán almacenamiento de OneDrive para la Empresa en Office 365 o en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="144df-113">If users aren't assigned and enabled with SharePoint Online licenses, they don't have OneDrive for Business storage in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="144df-114">El uso compartido de archivos seguirá funcionando en canales estándar, pero los usuarios no podrán compartir archivos en chats sin el almacenamiento de OneDrive para la Empresa en Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="144df-114">File sharing will continue to work in standard channels, but users won't be able to share files in chats without OneDrive for Business storage in Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="144df-115">Al almacenar archivos en la biblioteca de documentos de SharePoint Online y OneDrive para la Empresa, se siguen todas las reglas de cumplimiento configuradas en el nivel de inquilino.</span><span class="sxs-lookup"><span data-stu-id="144df-115">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="144df-116">La integración con SharePoint local no es compatible con Microsoft Teams en este momento.</span><span class="sxs-lookup"><span data-stu-id="144df-116">Integration with SharePoint On-premises is not supported for Microsoft Teams at this time.</span></span>

<span data-ttu-id="144df-117">A continuación se muestra el ejemplo de relaciones entre el equipo, el canal estándar y la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="144df-117">The following is the example of relationships between team, standard channel, and document library.</span></span>

<span data-ttu-id="144df-118">Para cada equipo, se crea un sitio de SharePoint y la carpeta **Documentos** compartidos es la carpeta predeterminada creada para el equipo.</span><span class="sxs-lookup"><span data-stu-id="144df-118">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team.</span></span> <span data-ttu-id="144df-119">Cada canal estándar, incluido el **canal General** (el canal predeterminado para cada equipo) tiene una carpeta en **Documentos compartidos.**</span><span class="sxs-lookup"><span data-stu-id="144df-119">Each standard channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![Diagrama de carpetas documentos compartidos en SharePoint Online.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> <span data-ttu-id="144df-121">En este momento no es posible reemplazar el sitio de SharePoint predeterminado y la biblioteca de documentos con otro.</span><span class="sxs-lookup"><span data-stu-id="144df-121">It's not currently possible to replace the default SharePoint site and document library with another one.</span></span> <span data-ttu-id="144df-122">Nos han comentado que les gustaría, por lo que estamos pensando en esa posibilidad.</span><span class="sxs-lookup"><span data-stu-id="144df-122">We've heard from you that you want it, and we're considering it.</span></span> <span data-ttu-id="144df-123">Revise el [mapa de ruta de Teams](https://aka.ms/teamsroadmap) o [Teams UserVoice](https://aka.ms/TeamsUserVoice) para estar al tanto de las próximas características.</span><span class="sxs-lookup"><span data-stu-id="144df-123">Check the [Teams Roadmap](https://aka.ms/teamsroadmap) or [Teams UserVoice](https://aka.ms/TeamsUserVoice) to stay on top of upcoming features.</span></span>

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

> [!TIP]
> <span data-ttu-id="144df-124">Para agregar una pestaña a su equipo que se vincula a una página de sitio de SharePoint existente o a la biblioteca de documentos de SharePoint existente:</span><span class="sxs-lookup"><span data-stu-id="144df-124">To add a tab to your team that links to an existing SharePoint site page or to your existing SharePoint document library:</span></span>
> 1. <span data-ttu-id="144df-125">Seleccione el signo más junto a las pestañas.</span><span class="sxs-lookup"><span data-stu-id="144df-125">Select the  plus sign next to the tabs.</span></span>
> 2. <span data-ttu-id="144df-126">Seleccione **SharePoint para una** página de sitio de SharePoint existente o **Biblioteca de documentos** para una biblioteca de documentos existente.</span><span class="sxs-lookup"><span data-stu-id="144df-126">Select either **SharePoint** for an existing SharePoint site page or **Document Library** for an existing document library.</span></span>
> 3. <span data-ttu-id="144df-127">Seleccione la página o biblioteca de documentos adecuada.</span><span class="sxs-lookup"><span data-stu-id="144df-127">Select the appropriate page or document library.</span></span>

<span data-ttu-id="144df-128">Para cada usuario, la carpeta de OneDrive **Archivos de chat de Microsoft Teams** se usa para almacenar todos los archivos compartidos en los chat privados con otros usuarios (1:1 o 1:varios), y los permisos se configuran automáticamente para restringir el acceso sólo a usuarios autorizados.</span><span class="sxs-lookup"><span data-stu-id="144df-128">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Diagrama de la carpeta de OneDrive denominada Archivos de chat de Microsoft Teams](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

<span data-ttu-id="144df-130">Tenga en cuenta que, en el caso de los equipos públicos, el sitio de grupo de SharePoint está aprovisionado con el acceso "Todos excepto los usuarios externos".</span><span class="sxs-lookup"><span data-stu-id="144df-130">Note that for public teams, the SharePoint team site is provisioned with "Everyone except external users" access.</span></span> <span data-ttu-id="144df-131">El equipo público no se muestra en Teams para personas que no son miembros de ese equipo.</span><span class="sxs-lookup"><span data-stu-id="144df-131">The public team isn't displayed in Teams for people who aren't members of that team.</span></span> <span data-ttu-id="144df-132">Sin embargo, pueden obtener acceso al contenido del sitio de grupo de SharePoint con la dirección URL del sitio de grupo de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="144df-132">However, they can access content on the SharePoint team site using the URL of the SharePoint team site.</span></span> 

## <a name="channel-files-tab"></a><span data-ttu-id="144df-133">Pestaña Archivos de canal</span><span class="sxs-lookup"><span data-stu-id="144df-133">Channel Files tab</span></span>

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

<span data-ttu-id="144df-134">La **pestaña** Archivos de Teams se parece mucho a la vista documentos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="144df-134">The **Files** tab in Teams closely resembles the SharePoint documents view.</span></span> <span data-ttu-id="144df-135">En la **pestaña** Archivos, los usuarios pueden:</span><span class="sxs-lookup"><span data-stu-id="144df-135">On the **Files** tab, users can:</span></span>

- <span data-ttu-id="144df-136">Vea opciones adicionales en el **menú Nuevo** archivo.</span><span class="sxs-lookup"><span data-stu-id="144df-136">See additional options in the **New** file menu.</span></span>
- <span data-ttu-id="144df-137">Sincronice archivos con su unidad local.</span><span class="sxs-lookup"><span data-stu-id="144df-137">Sync files to their local drive.</span></span>
- <span data-ttu-id="144df-138">En el **menú Todos los documentos,** cambie de la **vista** Lista a la **lista compacta** a la **vista Mosaicos.**</span><span class="sxs-lookup"><span data-stu-id="144df-138">On the **All Documents** menu, switch from **List** view to **Compact list** to **Tiles** view.</span></span>
- <span data-ttu-id="144df-139">Identifique archivos que necesiten atención o que tengan malware.</span><span class="sxs-lookup"><span data-stu-id="144df-139">Identify files that need attention or have malware.</span></span>
- <span data-ttu-id="144df-140">Vea inmediatamente si un archivo es de solo lectura o está desprotegiendo.</span><span class="sxs-lookup"><span data-stu-id="144df-140">Immediately see whether a file is read-only or checked out.</span></span>
- <span data-ttu-id="144df-141">Des check-out and check in files.</span><span class="sxs-lookup"><span data-stu-id="144df-141">Check out and check in files.</span></span>
- <span data-ttu-id="144df-142">Anclar, desanclar y cambiar el criterio de ordenación de los archivos.</span><span class="sxs-lookup"><span data-stu-id="144df-142">Pin, unpin, and change the sort order of files.</span></span>
- <span data-ttu-id="144df-143">Identificar qué archivos necesitan metadatos</span><span class="sxs-lookup"><span data-stu-id="144df-143">Identify which files need metadata</span></span>
- <span data-ttu-id="144df-144">Elija entre muchas más opciones de filtro.</span><span class="sxs-lookup"><span data-stu-id="144df-144">Choose from many more filter options.</span></span>
- <span data-ttu-id="144df-145">Agrupar archivos basados en encabezados de columna.</span><span class="sxs-lookup"><span data-stu-id="144df-145">Group files based on column headings.</span></span>
- <span data-ttu-id="144df-146">Modifique la configuración de columna (mover a la izquierda o a la derecha, ocultar) y el ancho de columna.</span><span class="sxs-lookup"><span data-stu-id="144df-146">Modify column settings (move left or right, hide) and column width.</span></span>

## <a name="default-link-type-setting"></a><span data-ttu-id="144df-147">Configuración predeterminada del tipo de vínculo</span><span class="sxs-lookup"><span data-stu-id="144df-147">Default link type setting</span></span>

<span data-ttu-id="144df-148">SharePoint y OneDrive tienen una configuración de administrador para especificar el tipo de vínculo predeterminado para los vínculos que se crean para un archivo.</span><span class="sxs-lookup"><span data-stu-id="144df-148">SharePoint and OneDrive have an admin setting for specifying the default link type for links that are created for a file.</span></span> <span data-ttu-id="144df-149">Teams está adoptando ese mismo enfoque al volver a la configuración que el administrador establece para SharePoint y OneDrive.</span><span class="sxs-lookup"><span data-stu-id="144df-149">Teams is adopting that same approach by reusing the settings that the admin sets for SharePoint and OneDrive.</span></span> <span data-ttu-id="144df-150">Más detalles sobre este enfoque se describen en [Cambiar el tipo de vínculo predeterminado cuando los usuarios obtienen vínculos para compartir.](/sharepoint/change-default-sharing-link)</span><span class="sxs-lookup"><span data-stu-id="144df-150">More details about this approach are described in [Change the default link type when users get links for sharing](/sharepoint/change-default-sharing-link).</span></span> 

## <a name="more-information"></a><span data-ttu-id="144df-151">Más información</span><span class="sxs-lookup"><span data-stu-id="144df-151">More information</span></span>

<span data-ttu-id="144df-152">Para obtener más información sobre cómo funciona SharePoint con Teams, vea [SharePoint y Teams: mejor juntos.](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)</span><span class="sxs-lookup"><span data-stu-id="144df-152">For more information about how SharePoint works with Teams, see [SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

<span data-ttu-id="144df-153">Para obtener más información sobre la experiencia de invitado en Teams, lea [¿Cómo es la experiencia de invitado?](guest-experience.md)</span><span class="sxs-lookup"><span data-stu-id="144df-153">To learn more about the guest experience in Teams, read [What the guest experience is like](guest-experience.md).</span></span>