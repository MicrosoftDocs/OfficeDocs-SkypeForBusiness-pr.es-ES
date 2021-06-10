---
title: Cómo SharePoint y OneDrive interactúan con Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint & OneDrive interacción con Teams; Almacenamiento privado de archivos de chat & interacción entre equipo, canal estándar, & biblioteca de documentos.
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 21abc840ddc740d7d842767c6c864d8ff5b598dd
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2021
ms.locfileid: "52855959"
---
# <a name="how-sharepoint-and-onedrive-interact-with-microsoft-teams"></a><span data-ttu-id="97493-103">Cómo SharePoint y OneDrive interactúan con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="97493-103">How SharePoint and OneDrive interact with Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="97493-104">Vea la siguiente sesión para obtener información sobre Teams interactúa con Azure Active Directory (AAD), Microsoft 365 Groups, Exchange, SharePoint y OneDrive: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="97493-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Microsoft 365 Groups, Exchange, SharePoint and OneDrive: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="97493-105">Cada equipo de Microsoft Teams tiene un sitio de grupo en SharePoint y cada canal estándar de un equipo obtiene una carpeta dentro de la biblioteca de documentos de sitio de grupo predeterminada.</span><span class="sxs-lookup"><span data-stu-id="97493-105">Each team in Microsoft Teams has a team site in SharePoint, and each standard channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="97493-106">Cada [canal privado](private-channels.md) obtiene su propio sitio de SharePoint independiente.</span><span class="sxs-lookup"><span data-stu-id="97493-106">Each [private channel](private-channels.md) gets its own, separate SharePoint site.</span></span>

<span data-ttu-id="97493-107">Los archivos compartidos dentro de una conversación se agregan automáticamente a la biblioteca de documentos y los permisos y las opciones de seguridad de archivos establecidas en SharePoint se reflejan automáticamente en Teams.</span><span class="sxs-lookup"><span data-stu-id="97493-107">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span> <span data-ttu-id="97493-108">Para ver el impacto de cambiar una dirección de sitio en SharePoint, lea [Cambiar una dirección de sitio](/sharepoint/change-site-address).</span><span class="sxs-lookup"><span data-stu-id="97493-108">To see the impact of changing a site address in SharePoint, read [Change a site address](/sharepoint/change-site-address).</span></span>

<span data-ttu-id="97493-109">Los archivos de chat privados se almacenan en la carpeta OneDrive del remitente y los permisos se conceden automáticamente a todos los participantes como parte del proceso de uso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="97493-109">Private chat files are stored in the sender's OneDrive folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="97493-110">Si a los usuarios no se les SharePoint licencias, no tienen OneDrive almacenamiento en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="97493-110">If users aren't assigned SharePoint licenses, they don't have OneDrive storage in Microsoft 365.</span></span> <span data-ttu-id="97493-111">El uso compartido de archivos funciona en canales estándar, pero los usuarios no podrán compartir archivos en chats sin OneDrive almacenamiento en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="97493-111">File sharing works in standard channels, but users won't be able to share files in chats without OneDrive storage in Microsoft 365.</span></span>

<span data-ttu-id="97493-112">Al almacenar los archivos en la SharePoint de documentos y OneDrive, se seguirán todas las reglas de cumplimiento configuradas en el nivel de la organización.</span><span class="sxs-lookup"><span data-stu-id="97493-112">By storing the files in the SharePoint document library and OneDrive, all compliance rules configured at the organization level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="97493-113">La integración con SharePoint Server no es compatible con Teams.</span><span class="sxs-lookup"><span data-stu-id="97493-113">Integration with SharePoint Server is not supported for Teams.</span></span>

<span data-ttu-id="97493-114">A continuación se muestra el ejemplo de relaciones entre el equipo, el canal estándar y la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="97493-114">The following is the example of relationships between team, standard channel, and document library.</span></span>

<span data-ttu-id="97493-115">Para cada equipo, se crea SharePoint sitio  y la carpeta Documentos compartidos es la carpeta predeterminada creada para el equipo.</span><span class="sxs-lookup"><span data-stu-id="97493-115">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team.</span></span> <span data-ttu-id="97493-116">Cada canal estándar, incluido el **canal General** (el canal predeterminado para cada equipo) tiene una carpeta en **Documentos compartidos.**</span><span class="sxs-lookup"><span data-stu-id="97493-116">Each standard channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![Diagrama de carpetas documentos compartidos en SharePoint.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

<span data-ttu-id="97493-118">El sitio SharePoint y la biblioteca de documentos predeterminadas no se pueden reemplazar por uno diferente.</span><span class="sxs-lookup"><span data-stu-id="97493-118">The default SharePoint site and document library can't be replaced with a different one.</span></span>

<span data-ttu-id="97493-119">Para cada usuario, la carpeta de OneDrive **Archivos de chat de Microsoft Teams** se usa para almacenar todos los archivos compartidos en los chat privados con otros usuarios (1:1 o 1:varios), y los permisos se configuran automáticamente para restringir el acceso sólo a usuarios autorizados.</span><span class="sxs-lookup"><span data-stu-id="97493-119">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Diagrama de la carpeta OneDrive llamada Microsoft Teams archivos de chat](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

<span data-ttu-id="97493-121">Tenga en cuenta que, en el caso de los equipos públicos, SharePoint sitio de grupo está aprovisionado con el acceso "Todos excepto los usuarios externos".</span><span class="sxs-lookup"><span data-stu-id="97493-121">Note that for public teams, the SharePoint team site is provisioned with "Everyone except external users" access.</span></span> <span data-ttu-id="97493-122">El equipo público no se muestra en Teams personas que no son miembros de ese equipo.</span><span class="sxs-lookup"><span data-stu-id="97493-122">The public team isn't displayed in Teams for people who aren't members of that team.</span></span> <span data-ttu-id="97493-123">Sin embargo, pueden obtener acceso al contenido del SharePoint de grupo mediante la dirección URL del SharePoint de grupo.</span><span class="sxs-lookup"><span data-stu-id="97493-123">However, they can access content on the SharePoint team site using the URL of the SharePoint team site.</span></span> 

## <a name="channel-files-tab"></a><span data-ttu-id="97493-124">Pestaña Archivos de canal</span><span class="sxs-lookup"><span data-stu-id="97493-124">Channel Files tab</span></span>

<span data-ttu-id="97493-125">La **pestaña** Archivos de Teams similar a la vista SharePoint documentos.</span><span class="sxs-lookup"><span data-stu-id="97493-125">The **Files** tab in Teams closely resembles the SharePoint documents view.</span></span> <span data-ttu-id="97493-126">En la **pestaña** Archivos, los usuarios pueden:</span><span class="sxs-lookup"><span data-stu-id="97493-126">On the **Files** tab, users can:</span></span>

- <span data-ttu-id="97493-127">Vea opciones adicionales en el **menú Nuevo** archivo.</span><span class="sxs-lookup"><span data-stu-id="97493-127">See additional options in the **New** file menu.</span></span>
- <span data-ttu-id="97493-128">Sincronice archivos con su unidad local.</span><span class="sxs-lookup"><span data-stu-id="97493-128">Sync files to their local drive.</span></span>
- <span data-ttu-id="97493-129">En el **menú Todos los documentos,** cambie de la **vista** Lista a la **lista compacta** a la **vista Mosaicos.**</span><span class="sxs-lookup"><span data-stu-id="97493-129">On the **All Documents** menu, switch from **List** view to **Compact list** to **Tiles** view.</span></span>
- <span data-ttu-id="97493-130">Identifique archivos que necesiten atención o que tengan malware.</span><span class="sxs-lookup"><span data-stu-id="97493-130">Identify files that need attention or have malware.</span></span>
- <span data-ttu-id="97493-131">Vea inmediatamente si un archivo es de solo lectura o está desprotegiendo.</span><span class="sxs-lookup"><span data-stu-id="97493-131">Immediately see whether a file is read-only or checked out.</span></span>
- <span data-ttu-id="97493-132">Des check-out and check in files.</span><span class="sxs-lookup"><span data-stu-id="97493-132">Check out and check in files.</span></span>
- <span data-ttu-id="97493-133">Anclar, desanclar y cambiar el criterio de ordenación de los archivos.</span><span class="sxs-lookup"><span data-stu-id="97493-133">Pin, unpin, and change the sort order of files.</span></span>
- <span data-ttu-id="97493-134">Identificar qué archivos necesitan metadatos</span><span class="sxs-lookup"><span data-stu-id="97493-134">Identify which files need metadata</span></span>
- <span data-ttu-id="97493-135">Elija entre muchas más opciones de filtro.</span><span class="sxs-lookup"><span data-stu-id="97493-135">Choose from many more filter options.</span></span>
- <span data-ttu-id="97493-136">Agrupar archivos basados en encabezados de columna.</span><span class="sxs-lookup"><span data-stu-id="97493-136">Group files based on column headings.</span></span>
- <span data-ttu-id="97493-137">Modifique la configuración de columna (mover a la izquierda o a la derecha, ocultar) y el ancho de columna.</span><span class="sxs-lookup"><span data-stu-id="97493-137">Modify column settings (move left or right, hide) and column width.</span></span>

## <a name="default-link-type-setting"></a><span data-ttu-id="97493-138">Configuración predeterminada del tipo de vínculo</span><span class="sxs-lookup"><span data-stu-id="97493-138">Default link type setting</span></span>

<span data-ttu-id="97493-139">El tipo de vínculo de uso compartido que se muestra de forma predeterminada cuando un usuario ha compartido un archivo se establece en el centro SharePoint administración.</span><span class="sxs-lookup"><span data-stu-id="97493-139">The type of sharing link shown by default when a user shared a file is set in the SharePoint admin center.</span></span> <span data-ttu-id="97493-140">Vea [Cambiar el tipo de vínculo predeterminado cuando los usuarios obtienen vínculos para compartir](/sharepoint/change-default-sharing-link) para obtener información.</span><span class="sxs-lookup"><span data-stu-id="97493-140">See [Change the default link type when users get links for sharing](/sharepoint/change-default-sharing-link) for information.</span></span>

## <a name="related-topics"></a><span data-ttu-id="97493-141">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="97493-141">Related topics</span></span>

<span data-ttu-id="97493-142">[SharePoint y Teams: mejor juntos.](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)</span><span class="sxs-lookup"><span data-stu-id="97493-142">[SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

[<span data-ttu-id="97493-143">Cómo es la experiencia de invitado</span><span class="sxs-lookup"><span data-stu-id="97493-143">What the guest experience is like</span></span>](guest-experience.md)