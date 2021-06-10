---
title: Usar la búsqueda de contenido en Microsoft Teams
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Obtenga información sobre cómo usar la búsqueda de contenido en el centro de cumplimiento de Microsoft 365 para buscar contenido Microsoft Teams almacenado en Exchange Online, SharePoint Online, OneDrive para la Empresa y OneNote.
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb63f3668ef03cdaf760a24ae1df0a815e7f282d
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2021
ms.locfileid: "52855809"
---
# <a name="use-content-search-in-microsoft-teams"></a><span data-ttu-id="d9e74-103">Usar la búsqueda de contenido en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d9e74-103">Use Content search in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="d9e74-104">La búsqueda de contenido de mensajes y archivos en [canales privados](private-channels.md) funciona de forma diferente que en los canales estándar.</span><span class="sxs-lookup"><span data-stu-id="d9e74-104">Content search of messages and files in [private channels](private-channels.md) work differently than in standard channels.</span></span> <span data-ttu-id="d9e74-105">Para obtener más información, vea [Búsqueda de contenido de canales privados.](#content-search-of-private-channels)</span><span class="sxs-lookup"><span data-stu-id="d9e74-105">To learn more, see [Content search of private channels](#content-search-of-private-channels).</span></span>

<span data-ttu-id="d9e74-106">La búsqueda de contenido proporciona una forma de consultar Microsoft Teams información que abarca Exchange, SharePoint en línea y OneDrive para la Empresa.</span><span class="sxs-lookup"><span data-stu-id="d9e74-106">Content search provides a way to query Microsoft Teams information spanning Exchange, SharePoint Online, and OneDrive for Business.</span></span>

<span data-ttu-id="d9e74-107">Para obtener más información, vea [Búsqueda de contenido en Microsoft 365](/microsoft-365/compliance/content-search).</span><span class="sxs-lookup"><span data-stu-id="d9e74-107">To learn more, see [Content search in Microsoft 365](/microsoft-365/compliance/content-search).</span></span>

<span data-ttu-id="d9e74-108">Por ejemplo,  con la búsqueda de contenido en su buzón de especificaciones de fabricación y en el sitio de Especificaciones de fabricación SharePoint Teams, puede buscar en conversaciones de canal estándar de Exchange, cargas de archivos y modificaciones de SharePoint Online y OneNote cambios.</span><span class="sxs-lookup"><span data-stu-id="d9e74-108">For example, using **Content search** against your Manufacturing Specs mailbox and Manufacturing Specs SharePoint site, you can search against Teams standard channel conversations from Exchange, file uploads and modifications from SharePoint Online, and OneNote changes.</span></span>

<span data-ttu-id="d9e74-109">También puede agregar criterios de consulta a la búsqueda **de contenido** para restringir los resultados devueltos.</span><span class="sxs-lookup"><span data-stu-id="d9e74-109">You can also add query criteria to the **Content Search** to narrow the results returned.</span></span> <span data-ttu-id="d9e74-110">En el ejemplo anterior, puede buscar contenido donde se usaron las palabras clave **"Nuevas** especificaciones de fábrica".</span><span class="sxs-lookup"><span data-stu-id="d9e74-110">In the above example, you can look for content where the keywords "**New Factory Specs"** were used.</span></span>

> [!TIP]
> <span data-ttu-id="d9e74-111">Después de agregar condiciones de búsqueda, puede exportar un informe o el contenido real al equipo para su análisis.</span><span class="sxs-lookup"><span data-stu-id="d9e74-111">After adding search conditions, you can export a report or the actual content to your computer for analysis.</span></span>

## <a name="content-search-of-private-channels"></a><span data-ttu-id="d9e74-112">Búsqueda de contenido de canales privados</span><span class="sxs-lookup"><span data-stu-id="d9e74-112">Content search of private channels</span></span>

<span data-ttu-id="d9e74-113">Los registros de los mensajes enviados en un canal privado se entregan en el buzón de todos los miembros del canal privado, en lugar de hacerlo en un buzón de grupo.</span><span class="sxs-lookup"><span data-stu-id="d9e74-113">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="d9e74-114">Los títulos de los registros tienen un formato que indica desde qué canal privado fueron enviados.</span><span class="sxs-lookup"><span data-stu-id="d9e74-114">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="d9e74-115">Dado que cada canal privado tiene su propia colección de sitios SharePoint independiente del sitio de grupo principal, los archivos de un canal privado se administran independientemente del equipo principal.</span><span class="sxs-lookup"><span data-stu-id="d9e74-115">Because each private channel has its own SharePoint site collection that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="d9e74-116">Teams no admite la búsqueda de contenido de un solo canal, por lo que se debe buscar a todo el equipo.</span><span class="sxs-lookup"><span data-stu-id="d9e74-116">Teams doesn't support content search of a single channel, so the whole team must be searched.</span></span> <span data-ttu-id="d9e74-117">Para realizar una búsqueda de contenido de un canal privado, busque en todo el equipo, la colección de sitios asociada con el canal privado (para incluir archivos) y los buzones de los miembros del canal privado (para incluir mensajes).</span><span class="sxs-lookup"><span data-stu-id="d9e74-117">To perform a content search of a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="d9e74-118">Siga estos pasos para identificar archivos y mensajes en un canal privado para incluirlos en la búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="d9e74-118">Use the following steps to identify files and messages in a private channel to include in  your content search.</span></span>

### <a name="include-private-channel-files-in-a-content-search"></a><span data-ttu-id="d9e74-119">Incluir archivos de canal privado en una búsqueda de contenido</span><span class="sxs-lookup"><span data-stu-id="d9e74-119">Include private channel files in a content search</span></span>

<span data-ttu-id="d9e74-120">Antes de realizar estos pasos, instale SharePoint Shell de administración en línea [y conéctese a SharePoint Online.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="d9e74-120">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

1. <span data-ttu-id="d9e74-121">Ejecute lo siguiente para obtener una lista de todas SharePoint colecciones de sitios asociadas con canales privados en el equipo.</span><span class="sxs-lookup"><span data-stu-id="d9e74-121">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```
2. <span data-ttu-id="d9e74-122">Ejecute el siguiente script de PowerShell para obtener una lista de todas las direcciones URL de la colección de sitios SharePoint asociadas con canales privados en el equipo y el id. de grupo de grupo principal.</span><span class="sxs-lookup"><span data-stu-id="d9e74-122">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. <span data-ttu-id="d9e74-123">Para cada id. de grupo o equipo, ejecute el siguiente script de PowerShell para identificar todos los sitios de canal privado relevantes.</span><span class="sxs-lookup"><span data-stu-id="d9e74-123">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a><span data-ttu-id="d9e74-124">Incluir mensajes de canal privado en una búsqueda de contenido</span><span class="sxs-lookup"><span data-stu-id="d9e74-124">Include private channel messages in a content search</span></span>

<span data-ttu-id="d9e74-125">Antes de realizar estos pasos, asegúrese de que tiene instalada la versión más reciente [Teams módulo de PowerShell.](teams-powershell-overview.md)</span><span class="sxs-lookup"><span data-stu-id="d9e74-125">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="d9e74-126">Ejecute lo siguiente para obtener una lista de canales privados en el equipo.</span><span class="sxs-lookup"><span data-stu-id="d9e74-126">Run the following to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. <span data-ttu-id="d9e74-127">Ejecute lo siguiente para obtener una lista de los miembros del canal privado.</span><span class="sxs-lookup"><span data-stu-id="d9e74-127">Run the following to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. <span data-ttu-id="d9e74-128">Incluya los buzones de todos los miembros de cada canal privado en el equipo como parte de la consulta de búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="d9e74-128">Include the mailboxes of all members from each private channel in the team as part of your content search query.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d9e74-129">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d9e74-129">Related topics</span></span>

- [<span data-ttu-id="d9e74-130">Casos de exhibición de documentos electrónicos en el Centro Microsoft 365 cumplimiento</span><span class="sxs-lookup"><span data-stu-id="d9e74-130">eDiscovery cases in the Microsoft 365 Compliance Center</span></span>](/Office365/SecurityCompliance/ediscovery-cases)