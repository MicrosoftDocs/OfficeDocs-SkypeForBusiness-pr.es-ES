---
title: Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint Online & la interacción de OneDrive para la empresa con Teams; almacenamiento de archivos de conversaciones privadas & interacción entre el equipo, el canal estándar, & biblioteca de documentos.
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fd34bf368667fcfa5776de40cad0d1444440805a
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137260"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="064ae-103">Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="064ae-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="064ae-104">Vea la siguiente sesión para obtener información sobre cómo Teams interactúa con Azure Active Directory (AAD), grupos de Office 365, Exchange, SharePoint y OneDrive para la empresa: [bases de Microsoft Teams](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="064ae-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Office 365 Groups, Exchange, SharePoint and OneDrive for Business: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="064ae-105">Cada equipo de Microsoft Teams tiene un sitio de grupo en SharePoint Online y cada canal estándar de un equipo obtiene una carpeta dentro de la biblioteca de documentos predeterminada del sitio de grupo.</span><span class="sxs-lookup"><span data-stu-id="064ae-105">Each team in Microsoft Teams has a team site in SharePoint Online, and each standard channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="064ae-106">Los archivos compartidos en una conversación se agregan automáticamente a la biblioteca de documentos y los permisos y las opciones de seguridad de archivos establecidos en SharePoint se reflejan automáticamente en Teams.</span><span class="sxs-lookup"><span data-stu-id="064ae-106">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span> <span data-ttu-id="064ae-107">Para ver el impacto de cambiar la dirección de un sitio en SharePoint, lea [cambiar la dirección de un sitio](https://docs.microsoft.com/sharepoint/change-site-address).</span><span class="sxs-lookup"><span data-stu-id="064ae-107">To see the impact of changing a site address in SharePoint, read [Change a site address](https://docs.microsoft.com/sharepoint/change-site-address).</span></span>

> [!NOTE]
> <span data-ttu-id="064ae-108">Este artículo se aplica solo a los canales estándar.</span><span class="sxs-lookup"><span data-stu-id="064ae-108">This article applies only to standard channels.</span></span> <span data-ttu-id="064ae-109">La arquitectura de los canales privados es diferente de la de los canales estándar.</span><span class="sxs-lookup"><span data-stu-id="064ae-109">The architecture for private channels is different from standard channels.</span></span> <span data-ttu-id="064ae-110">Cada canal privado tiene su propia colección de sitios de SharePoint que es independiente del sitio de grupo primario.</span><span class="sxs-lookup"><span data-stu-id="064ae-110">Each private channel has its own SharePoint site collection that's separate from the parent team site.</span></span> <span data-ttu-id="064ae-111">Para obtener más información, consulte [canales privados en Microsoft Teams](private-channels.md).</span><span class="sxs-lookup"><span data-stu-id="064ae-111">To learn more, see [Private channels in Microsoft Teams](private-channels.md).</span></span>

<span data-ttu-id="064ae-112">Los archivos de conversación privada se almacenan en la carpeta del remitente de OneDrive para la empresa y los permisos se conceden automáticamente a todos los participantes como parte del proceso de uso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="064ae-112">Private chat files are stored in the sender's OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="064ae-113">Si los usuarios no tienen asignada ni habilitada licencias de SharePoint Online, no tienen almacenamiento de OneDrive para la empresa en Office 365.</span><span class="sxs-lookup"><span data-stu-id="064ae-113">If users aren't assigned and enabled with SharePoint Online licenses, they don't have OneDrive for Business storage in Office 365.</span></span> <span data-ttu-id="064ae-114">El uso compartido de archivos seguirá funcionando en canales estándar, pero los usuarios no podrán compartir archivos en chats sin el almacenamiento de OneDrive para la empresa en Office 365.</span><span class="sxs-lookup"><span data-stu-id="064ae-114">File sharing will continue to work in standard channels, but users won't be able to share files in chats without OneDrive for Business storage in Office 365.</span></span>

<span data-ttu-id="064ae-115">Al almacenar archivos en la biblioteca de documentos de SharePoint Online y OneDrive para la Empresa, se siguen todas las reglas de cumplimiento configuradas en el nivel de inquilino.</span><span class="sxs-lookup"><span data-stu-id="064ae-115">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="064ae-116">En este momento, la integración con SharePoint local no es compatible con Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="064ae-116">Integration with SharePoint On-premises is not supported for Microsoft Teams at this time.</span></span>

<span data-ttu-id="064ae-117">A continuación se encuentra el ejemplo de relaciones entre equipo, canal estándar y biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="064ae-117">The following is the example of relationships between team, standard channel, and document library.</span></span>

<span data-ttu-id="064ae-118">Para cada equipo, se crea un sitio de SharePoint y la carpeta **documentos compartidos** es la carpeta predeterminada creada para el equipo.</span><span class="sxs-lookup"><span data-stu-id="064ae-118">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team.</span></span> <span data-ttu-id="064ae-119">Cada canal estándar, incluido el canal **General** (el canal predeterminado de cada equipo), tiene una carpeta en **documentos compartidos**.</span><span class="sxs-lookup"><span data-stu-id="064ae-119">Each standard channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![Diagrama de carpetas de documentos compartidos en SharePoint Online.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> <span data-ttu-id="064ae-121">En este momento no es posible reemplazar el sitio de SharePoint predeterminado y la biblioteca de documentos con otro.</span><span class="sxs-lookup"><span data-stu-id="064ae-121">It's not currently possible to replace the default SharePoint site and document library with another one.</span></span> <span data-ttu-id="064ae-122">Nos han comentado que les gustaría, por lo que estamos pensando en esa posibilidad.</span><span class="sxs-lookup"><span data-stu-id="064ae-122">We've heard from you that you want it, and we're considering it.</span></span> <span data-ttu-id="064ae-123">Revise el [mapa de ruta de Teams](https://aka.ms/teamsroadmap) o [Teams UserVoice](https://aka.ms/TeamsUserVoice) para estar al tanto de las próximas características.</span><span class="sxs-lookup"><span data-stu-id="064ae-123">Check the [Teams Roadmap](https://aka.ms/teamsroadmap) or [Teams UserVoice](https://aka.ms/TeamsUserVoice) to stay on top of upcoming features.</span></span>

> [!TIP]
> <span data-ttu-id="064ae-124">Para agregar una pestaña a su equipo que tenga un vínculo a una página de un sitio de SharePoint existente o a la biblioteca de documentos de SharePoint existente:</span><span class="sxs-lookup"><span data-stu-id="064ae-124">To add a tab to your team that links to an existing SharePoint site page or to your existing SharePoint document library:</span></span>
> 1. <span data-ttu-id="064ae-125">Seleccione el signo más situado junto a las pestañas.</span><span class="sxs-lookup"><span data-stu-id="064ae-125">Select the  plus sign next to the tabs.</span></span>
> 2. <span data-ttu-id="064ae-126">Seleccione **SharePoint** para una página de sitio de SharePoint existente o **biblioteca de documentos** para una biblioteca de documentos existente.</span><span class="sxs-lookup"><span data-stu-id="064ae-126">Select either **SharePoint** for an existing SharePoint site page or **Document Library** for an existing document library.</span></span>
> 3. <span data-ttu-id="064ae-127">Seleccione la página o biblioteca de documentos adecuada.</span><span class="sxs-lookup"><span data-stu-id="064ae-127">Select the appropriate page or document library.</span></span>

<span data-ttu-id="064ae-128">Para cada usuario, la carpeta de OneDrive **Archivos de chat de Microsoft Teams** se usa para almacenar todos los archivos compartidos en los chat privados con otros usuarios (1:1 o 1:varios), y los permisos se configuran automáticamente para restringir el acceso sólo a usuarios autorizados.</span><span class="sxs-lookup"><span data-stu-id="064ae-128">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Diagrama de la carpeta de OneDrive denominada archivos de chat de Microsoft Teams](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

## <a name="channel-files-tab"></a><span data-ttu-id="064ae-130">Ficha archivos de canal</span><span class="sxs-lookup"><span data-stu-id="064ae-130">Channel Files tab</span></span>

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

<span data-ttu-id="064ae-131">La pestaña **archivos** de Teams es muy similar a la vista documentos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="064ae-131">The **Files** tab in Teams closely resembles the SharePoint documents view.</span></span> <span data-ttu-id="064ae-132">En la pestaña **archivos** , los usuarios pueden:</span><span class="sxs-lookup"><span data-stu-id="064ae-132">On the **Files** tab, users can:</span></span>

- <span data-ttu-id="064ae-133">Consulte Opciones adicionales en el menú **nuevo** archivo.</span><span class="sxs-lookup"><span data-stu-id="064ae-133">See additional options in the **New** file menu.</span></span>
- <span data-ttu-id="064ae-134">Sincronizar archivos con su unidad local.</span><span class="sxs-lookup"><span data-stu-id="064ae-134">Sync files to their local drive.</span></span>
- <span data-ttu-id="064ae-135">En el menú **todos los documentos** , cambie de la vista de **lista** a la de **lista compacta** a vista de **mosaicos** .</span><span class="sxs-lookup"><span data-stu-id="064ae-135">On the **All Documents** menu, switch from **List** view to **Compact list** to **Tiles** view.</span></span>
- <span data-ttu-id="064ae-136">Identifique los archivos que necesitan atención o tienen malware.</span><span class="sxs-lookup"><span data-stu-id="064ae-136">Identify files that need attention or have malware.</span></span>
- <span data-ttu-id="064ae-137">Ver inmediatamente si un archivo es de solo lectura o desprotegido.</span><span class="sxs-lookup"><span data-stu-id="064ae-137">Immediately see whether a file is read-only or checked out.</span></span>
- <span data-ttu-id="064ae-138">Desproteger y proteger archivos.</span><span class="sxs-lookup"><span data-stu-id="064ae-138">Check out and check in files.</span></span>
- <span data-ttu-id="064ae-139">Anclar, desanclar y cambiar el orden de los archivos.</span><span class="sxs-lookup"><span data-stu-id="064ae-139">Pin, unpin, and change the sort order of files.</span></span>
- <span data-ttu-id="064ae-140">Identificar qué archivos necesitan metadatos</span><span class="sxs-lookup"><span data-stu-id="064ae-140">Identify which files need metadata</span></span>
- <span data-ttu-id="064ae-141">Elija entre más opciones de filtro.</span><span class="sxs-lookup"><span data-stu-id="064ae-141">Choose from many more filter options.</span></span>
- <span data-ttu-id="064ae-142">Agrupar archivos en función de los encabezados de columna.</span><span class="sxs-lookup"><span data-stu-id="064ae-142">Group files based on column headings.</span></span>
- <span data-ttu-id="064ae-143">Modificar la configuración de las columnas (desplazarse a la izquierda o a la derecha, ocultar) y ancho de columna.</span><span class="sxs-lookup"><span data-stu-id="064ae-143">Modify column settings (move left or right, hide) and column width.</span></span>

## <a name="default-link-type-setting"></a><span data-ttu-id="064ae-144">Configuración de tipo de vínculo predeterminado</span><span class="sxs-lookup"><span data-stu-id="064ae-144">Default link type setting</span></span>

<span data-ttu-id="064ae-145">SharePoint y OneDrive tienen una configuración de administrador para especificar el tipo de vínculo predeterminado para los vínculos que se crean para un archivo.</span><span class="sxs-lookup"><span data-stu-id="064ae-145">SharePoint and OneDrive have an admin setting for specifying the default link type for links that are created for a file.</span></span> <span data-ttu-id="064ae-146">Teams adopta ese mismo enfoque al reutilizar la configuración que los conjuntos de administradores para SharePoint y OneDrive.</span><span class="sxs-lookup"><span data-stu-id="064ae-146">Teams is adopting that same approach by reusing the settings that the admin sets for SharePoint and OneDrive.</span></span> <span data-ttu-id="064ae-147">Se describen más detalles sobre este enfoque en [cambiar el tipo de vínculo predeterminado cuando los usuarios obtienen vínculos para compartir](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span><span class="sxs-lookup"><span data-stu-id="064ae-147">More details about this approach are described in [Change the default link type when users get links for sharing](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span></span> 

## <a name="more-information"></a><span data-ttu-id="064ae-148">Más información</span><span class="sxs-lookup"><span data-stu-id="064ae-148">More information</span></span>

<span data-ttu-id="064ae-149">Para obtener más información acerca de cómo funciona SharePoint con Teams, vea [SharePoint y Teams: mejor juntos](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span><span class="sxs-lookup"><span data-stu-id="064ae-149">For more information about how SharePoint works with Teams, see [SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

<span data-ttu-id="064ae-150">Para obtener más información sobre la experiencia de invitado en Teams, lea [el aspecto de la experiencia de invitado](guest-experience.md).</span><span class="sxs-lookup"><span data-stu-id="064ae-150">To learn more about the guest experience in Teams, read [What the guest experience is like](guest-experience.md).</span></span>

