---
title: Usar la búsqueda de contenido en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anach
search.appverid: MET150
f1.keywords:
- NOCSH
description: Obtenga más información sobre la búsqueda de contenido en Microsoft Teams y sobre cómo buscar con las conversaciones de canal de Exchange, las cargas de archivos y las modificaciones de SharePoint y los cambios de OneNote.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 222b57021a259795823031d9855304d1ecf27f4f
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825348"
---
<a name="use-content-search-in-microsoft-teams"></a><span data-ttu-id="87366-103">Usar la búsqueda de contenido en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="87366-103">Use Content Search in Microsoft Teams</span></span>
=====================================

> [!NOTE]
> <span data-ttu-id="87366-104">La búsqueda de contenido de mensajes y archivos de [canales privados](private-channels.md) funciona de manera diferente que en los canales estándar.</span><span class="sxs-lookup"><span data-stu-id="87366-104">Content search of messages and files in [private channels](private-channels.md) work differently than in standard channels.</span></span> <span data-ttu-id="87366-105">Para obtener más información, consulta [búsqueda de contenido de canales privados](#content-search-of-private-channels).</span><span class="sxs-lookup"><span data-stu-id="87366-105">To learn more, see [Content search of private channels](#content-search-of-private-channels).</span></span>

<span data-ttu-id="87366-106">Búsqueda de contenido proporciona una manera de consultar información de Microsoft Teams en Exchange, SharePoint Online y OneDrive para la empresa.</span><span class="sxs-lookup"><span data-stu-id="87366-106">Content Search provides a way to query Microsoft Teams information spanning Exchange, SharePoint Online, and OneDrive for Business.</span></span>

<span data-ttu-id="87366-107">Para obtener más información, lea [búsqueda de contenido en Office 365](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a).</span><span class="sxs-lookup"><span data-stu-id="87366-107">To learn more, read [Content Search in Office 365](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a).</span></span>

<span data-ttu-id="87366-108">Por ejemplo, mediante la **búsqueda de contenido** en el sitio de SharePoint especificaciones de fabricación, buzón y especificaciones de fabricación, puede buscar entre las conversaciones de canal estándar de Teams de Exchange, las cargas de archivos y las modificaciones de SharePoint Online y los cambios de OneNote.</span><span class="sxs-lookup"><span data-stu-id="87366-108">For example, using **Content Search** against your Manufacturing Specs mailbox and Manufacturing Specs SharePoint site, you can search against Teams standard channel conversations from Exchange, file uploads and modifications from SharePoint Online, and OneNote changes.</span></span>

<span data-ttu-id="87366-p102">También puede Agregar criterios de consulta a la **búsqueda de contenido** para restringir los resultados devueltos. En el ejemplo anterior, puede buscar contenido en el que se hayan usado las palabras clave "**nuevas especificaciones de fábrica"** .</span><span class="sxs-lookup"><span data-stu-id="87366-p102">You can also add query criteria to the **Content Search** to narrow the results returned. In the above example, you can look for content where the keywords “**New Factory Specs”** were used.</span></span>

> [!TIP]
> <span data-ttu-id="87366-111">Después de agregar condiciones de búsqueda, puede exportar un informe o los datos a su equipo para analizarlos.</span><span class="sxs-lookup"><span data-stu-id="87366-111">After adding search conditions, you can export a report or the data to your computer for analysis.</span></span>

## <a name="content-search-of-private-channels"></a><span data-ttu-id="87366-112">Búsqueda de contenido de canales privados</span><span class="sxs-lookup"><span data-stu-id="87366-112">Content search of private channels</span></span>

<span data-ttu-id="87366-113">Los registros de los mensajes enviados en un canal privado se entregan en el buzón de todos los miembros del canal privado, en lugar de hacerlo en un buzón de grupo.</span><span class="sxs-lookup"><span data-stu-id="87366-113">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="87366-114">El formato de los títulos de los registros indica el canal privado desde el que se enviaron.</span><span class="sxs-lookup"><span data-stu-id="87366-114">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="87366-115">Como cada canal privado tiene su propia colección de sitios de SharePoint que es independiente del sitio de grupo primario, los archivos de un canal privado se administran independientemente del equipo principal.</span><span class="sxs-lookup"><span data-stu-id="87366-115">Because each private channel has its own SharePoint site collection that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="87366-116">Teams no admite la búsqueda de contenido de un único canal, por lo que se debe buscar en todo el equipo.</span><span class="sxs-lookup"><span data-stu-id="87366-116">Teams doesn't support content search of a single channel, so the whole team must be searched.</span></span> <span data-ttu-id="87366-117">Para realizar una búsqueda de contenido de un canal privado, busque en el equipo, la colección de sitios asociada al canal privado (para incluir archivos) y buzones de miembros de canales privados (para incluir mensajes).</span><span class="sxs-lookup"><span data-stu-id="87366-117">To perform a content search of a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="87366-118">Siga estos pasos para identificar los archivos y mensajes de un canal privado para incluirlos en la búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="87366-118">Use the following steps to identify files and messages in a private channel to include in  your content search.</span></span>

### <a name="include-private-channel-files-in-a-content-search"></a><span data-ttu-id="87366-119">Incluir archivos de canal privado en una búsqueda de contenido</span><span class="sxs-lookup"><span data-stu-id="87366-119">Include private channel files in a content search</span></span>

<span data-ttu-id="87366-120">Antes de realizar estos pasos, instale el [Shell de administración de SharePoint Online y conéctese a SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="87366-120">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

1. <span data-ttu-id="87366-121">Ejecute lo siguiente para obtener una lista de todas las colecciones de sitios de SharePoint asociadas a los canales privados en el equipo.</span><span class="sxs-lookup"><span data-stu-id="87366-121">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```
2. <span data-ttu-id="87366-122">Ejecute el siguiente script de PowerShell para obtener una lista de todas las direcciones URL de la colección de sitios de SharePoint asociadas a los canales privados en el equipo y el identificador del grupo de equipos primario.</span><span class="sxs-lookup"><span data-stu-id="87366-122">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. <span data-ttu-id="87366-123">Para cada uno de los IDENTIFICADOres de grupo o equipo, ejecute el siguiente script de PowerShell para identificar todos los sitios de canal privado pertinentes.</span><span class="sxs-lookup"><span data-stu-id="87366-123">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “e8195240-4a70-4830-9106-80193cf717cb“
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a><span data-ttu-id="87366-124">Incluir mensajes de canal privado en una búsqueda de contenido</span><span class="sxs-lookup"><span data-stu-id="87366-124">Include private channel messages in a content search</span></span>

<span data-ttu-id="87366-125">Antes de realizar estos pasos, asegúrese de que tiene instalada la [última versión del módulo de PowerShell de Teams](teams-powershell-overview.md) .</span><span class="sxs-lookup"><span data-stu-id="87366-125">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="87366-126">Ejecute lo siguiente para obtener una lista de canales privados en el equipo.</span><span class="sxs-lookup"><span data-stu-id="87366-126">Run the following to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. <span data-ttu-id="87366-127">Ejecute lo siguiente para obtener una lista de miembros del canal privado.</span><span class="sxs-lookup"><span data-stu-id="87366-127">Run the following to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. <span data-ttu-id="87366-128">Incluya los buzones de todos los miembros de cada canal privado del equipo como parte de la consulta de búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="87366-128">Include the mailboxes of all members from each private channel in the team as part of your content search query.</span></span>

## <a name="related-topics"></a><span data-ttu-id="87366-129">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="87366-129">Related topics</span></span>

- [<span data-ttu-id="87366-130">casos de eDiscovery en el centro de cumplimiento de & de seguridad de Office 365</span><span class="sxs-lookup"><span data-stu-id="87366-130">eDiscovery cases in the Office 365 Security & Compliance Center</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/ediscovery-cases) 